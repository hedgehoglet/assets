# Forage

Hedgehoglet's open asset library, served at [assets.hedgehoglet.dev](https://assets.hedgehoglet.dev) via GitHub Pages.

## Adding an asset

1. Drop the file into `assets/shared/<format>/`
2. Add an entry to `assets/registry.json`:

```json
{
  "file": "myfile.csv",
  "path": "assets/shared/csv/myfile.csv",
  "icon": "📊",
  "format": "csv",
  "description": "One sentence describing the asset.",
  "tags": ["tag1", "tag2"],
  "size": "12 KB",
  "added": "2024-06-01"
}
```

No other changes needed.
