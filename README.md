# ext-pack Registry

Public registry for browser extension packs.

## What is this?

This repository serves as the central registry for [ext-pack](https://github.com/IFAKA/ext-pack) - a tool for bundling, publishing, and installing browser extension packs.

## How it works

1. Users publish packs via `ext-pack publish`
2. Pack files are uploaded as GitHub releases
3. This registry index is updated via pull request
4. GitHub Actions validates and auto-merges
5. Users can install by name: `ext-pack install <pack-name>`

## Registry Index

The `registry.json` file contains metadata for all published packs:

```json
{
  "version": "1.0",
  "updated": "2026-02-15T00:00:00Z",
  "packs": {
    "example-pack": {
      "id": "example-pack",
      "name": "Example Pack",
      "description": "An example extension pack",
      "author": {
        "name": "Author Name",
        "github": "username"
      },
      "version": "1.0.0",
      "extensions": 3,
      "size": 1234567,
      "downloads": 0,
      "stars": 0,
      "tags": ["productivity", "privacy"],
      "created": "2026-02-15",
      "updated": "2026-02-15T00:00:00Z",
      "url": "https://github.com/ext-pack/registry/releases/download/example-pack-v1.0.0/example-pack.extpack"
    }
  }
}
```

## Publishing a Pack

1. Install ext-pack: `npm install -g ext-pack`
2. Create your pack: `ext-pack create`
3. Publish: `ext-pack publish my-pack.extpack`
4. Wait for auto-merge (~2 minutes)

## Guidelines

### Pack Requirements

- ✅ Valid `.extpack` format (JSON)
- ✅ All extensions bundled (no external dependencies)
- ✅ Size < 100MB (compressed)
- ✅ No malware or malicious code
- ✅ Descriptive name and description
- ✅ Appropriate tags

### Prohibited Content

- ❌ Malware, spyware, or malicious code
- ❌ Copyright-infringing content
- ❌ Packs that violate browser extension policies
- ❌ Offensive or inappropriate content

## Browse Packs

Visit the web interface: **https://ext-pack.github.io/registry**

Or search from CLI:
```bash
ext-pack search productivity
ext-pack search --tag privacy
```

## Contributing

Found an issue with a pack? Open an issue with the pack name and details.

Want to help maintain the registry? See [CONTRIBUTING.md](CONTRIBUTING.md)

## License

Registry data: CC0 (Public Domain)
Individual packs: See respective pack licenses
