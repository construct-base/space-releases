# Construct Space Releases

Central release repository for all Construct spaces. Automated via GitHub Actions.

## How it works

1. A `space-*` repo pushes a version tag (`v0.2.0`)
2. Its release workflow builds a tarball and dispatches to this repo
3. The `collect` workflow here downloads the tarball into `spaces/<name>/` and updates `index.json`

## Structure

```
spaces/
  ai/
    v0.2.0.tar.gz
  architect/
    v0.2.0.tar.gz
  ...
index.json          # Registry of all spaces + latest versions
```

## index.json format

```json
{
  "version": 1,
  "updated_at": "2026-02-25T...",
  "spaces": [
    {
      "id": "ai",
      "name": "AI",
      "version": "0.2.0",
      "description": "...",
      "icon": "i-lucide-sparkles",
      "repo": "construct-base/space-ai",
      "tarball": "spaces/ai/v0.2.0.tar.gz"
    }
  ]
}
```
