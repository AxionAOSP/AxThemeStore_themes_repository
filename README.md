# AxThemeStore Themes Repository

Official theme repository for AxionOS Theme Store application.

## Repository Structure

```
AxThemeStore_themes_repository/
├── apks/                    # Theme APK files
│   ├── IconPackAcherusUnified.apk
│   ├── IconPackGradiconUnified.apk
│   ├── IconPackLornUnified.apk
│   └── IconPackPUIUnified.apk
├── previews/                # Preview images for themes
│   ├── acherus_preview.png
├── docs/                    # Documentation
│   └── CONTRIBUTING.md     # Contribution guidelines
└── themes.json             # Theme metadata catalog
```

## Theme Catalog Format

The `themes.json` file follows this structure:

```json
{
  "version": 2,
  "lastUpdated": "ISO 8601 timestamp",
  "repository": {
    "name": "Repository name",
    "description": "Repository description",
    "maintainer": "Maintainer name",
    "baseUrl": "Base URL for assets"
  },
  "components": [...],
  "categories": [...],
  "themes": [...]
}
```

## Adding New Themes

1. Place APK file in `apks/` directory
2. Add preview image (1920x1080 recommended) to `previews/` directory
3. Update `themes.json` with theme metadata
4. Follow naming convention: `IconPack{Name}Unified.apk`
5. Ensure all URLs point to correct GitHub raw content URLs

## Preview Image Guidelines

- **Resolution**: 1920x1080 (16:9 aspect ratio)
- **Format**: PNG or JPEG
- **Content**: Show key features of the theme (status bar, quick settings, etc.)
- **Naming**: `{theme_id}_preview.png`

## Component IDs

Supported component IDs for unified themes:
- `android` - Android framework icons
- `systemui` - System UI icons
- `wifi` - WiFi indicator icons
- `signal` - Mobile signal icons
- `battery` - Battery indicator icons

## Version History

- **v2** (2025-12-12): Added Gradicon, Lorn, and PUI themes. Reorganized repository structure.
- **v1** (2025-12-09): Initial release with Acherus theme and UI styles.

## License

Themes are provided by their respective authors. Please check individual theme licenses.

## Contributing

See [CONTRIBUTING.md](docs/CONTRIBUTING.md) for guidelines on submitting new themes.
