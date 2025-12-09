# Contributing to AxThemeStore Themes Repository

Thank you for your interest in contributing themes to the AxionOS Theme Store!

## Submission Guidelines

### 1. Theme Requirements

#### Technical Requirements
- **Minimum SDK**: 36 (Android 16)
- **Package Format**: APK (Android Package)
- **Overlay Type**: Unified theme package preferred
- **Compatibility**: Must work with AxionOS theme engine

#### Quality Requirements
- Icons must have high quality
- Consistent design language across all icons
- No broken or missing resources
- Proper attribution for any third-party assets

### 2. File Naming Conventions

#### APK Files
```
IconPack{ThemeName}Unified.apk
```
Examples:
- `IconPackAcherusUnified.apk`
- `IconPackGradiconUnified.apk`

#### Preview Images
```
{theme_id}_preview.png
```
Examples:
- `acherus_preview.png`
- `gradicon_preview.png`

### 3. Preview Image Specifications

- **Resolution**: 1920x1080 pixels (16:9 aspect ratio)
- **Format**: PNG (preferred) or JPEG
- **File Size**: Under 500KB
- **Content Requirements**:
  - Show status bar with WiFi, signal, and battery icons
  - Include quick settings panel if applicable
  - Display 2-3 key features of your theme
  - Use clean, uncluttered composition
  - Include theme name/branding

### 4. Theme Metadata

When adding your theme to `themes.json`, include:

```json
{
  "id": "unique_theme_id",
  "name": "Display Name",
  "description": "Detailed description (100-200 characters)",
  "author": "Your Name or Team",
  "version": "1.0.0",
  "versionCode": 1,
  "minSdk": 35,
  "previewImages": [
    "https://raw.githubusercontent.com/.../previews/your_preview.png"
  ],
  "category": "icon_themes",
  "tags": ["relevant", "tags", "here"],
  "isUnified": true,
  "overlays": [
    {
      "componentId": "unified",
      "packageName": "com.android.theme.icon_pack.yourtheme",
      "targets": ["android", "systemui", "wifi", "signal", "battery"],
      "downloadUrl": "https://raw.githubusercontent.com/.../apks/YourTheme.apk",
      "fileSize": 123456,
      "enabled": true
    }
  ]
}
```

### 5. AndroidManifest.xml Structure

Your theme APK must include a properly structured `AndroidManifest.xml`:

```xml
<?xml version="1.0" encoding="utf-8"?>
<manifest xmlns:android="http://schemas.android.com/apk/res/android"
    package="com.android.theme.icon_pack.yourtheme"
    android:versionCode="1"
    android:versionName="1.0">
    
    <application 
        android:label="Your Theme Name" 
        android:hasCode="false">
        
        <!-- Theme metadata: comma-separated list of supported components -->
        <meta-data
            android:name="axion_theme"
            android:value="android,battery,signal,systemui,wifi" />
    </application>
</manifest>
```

**Building from android studio:**
- just remember to add the axion theme metadata

**Theme Metadata:**

The `axion_theme` meta-data specifies which components your theme provides:

```xml
<meta-data
    android:name="axion_theme"
    android:value="component1,component2,component3" />
```

The `axion_shapes` meta-data specifies which components your icon shape theme provides:

```xml
<meta-data
    android:name="axion_shapes"
    android:value="component1,component2,component3" />
```

**Available Components:**
- `android` - Android framework icons
- `systemui` - System UI icons
- `wifi` - WiFi indicator icons
- `signal` - Mobile signal icons
- `battery` - Battery indicator icons

**Example Combinations:**

Full system theme:
```xml
android:value="android,battery,signal,systemui,wifi"
```

Status bar icons only:
```xml
android:value="battery,signal,wifi"
```

See [AndroidManifest.xml.template](AndroidManifest.xml.template) for a complete template.

### 6. Submission Process

1. **Fork the Repository**
   ```bash
   git clone https://github.com/AxionAOSP/AxThemeStore_themes_repository.git
   cd AxThemeStore_themes_repository
   ```

2. **Add Your Files**
   ```bash
   # Add APK to apks directory
   cp YourTheme.apk apks/IconPackYourThemeUnified.apk
   
   # Add preview image to previews directory
   cp preview.png previews/yourtheme_preview.png
   ```

3. **Update themes.json**
   - Add your theme entry to the `themes` array
   - Update `lastUpdated` timestamp
   - Ensure proper JSON formatting

4. **Test Locally**
   - Verify JSON is valid: `cat themes.json | jq`
   - Check file sizes are reasonable
   - Ensure URLs will be correct after merge

5. **Submit Pull Request**
   - Create descriptive PR title: "Add [Theme Name] icon theme"
   - Include screenshots in PR description
   - Mention any special requirements or notes

### 6. Package Name Convention

Use this format for package names:
```
com.android.theme.icon_pack.{themename}
```

Examples:
- `com.android.theme.icon_pack.acherus`
- `com.android.theme.icon_pack.gradicon`

### 7. Supported Components

Your unified theme can target these components:

| Component ID | Description | Target Package |
|--------------|-------------|----------------|
| `android` | Framework icons | `android` |
| `systemui` | System UI icons | `com.android.systemui` |
| `wifi` | WiFi indicators | `com.android.systemui` |
| `signal` | Signal indicators | `com.android.systemui` |
| `battery` | Battery indicators | `com.android.systemui` |

### 8. Categories and Tags

#### Categories
- `icon_themes` - System icon themes
- `ui_style` - UI style presets (reserved for official styles)

#### Recommended Tags
- Design style: `minimal`, `gradient`, `bold`, `clean`, `modern`
- Components: `statusbar`, `systemui`, `android`, `icons`
- Inspiration: `pixel`, `material`, `ios`, `custom`
- Color: `colorful`, `monochrome`, `dark`, `light`

### 9. Version Updates

When updating an existing theme:

1. Increment `versionCode` by 1
2. Update `version` following semantic versioning
3. Update `fileSize` if changed
4. Update preview images if design changed significantly

### 10. Quality Checklist

Before submitting, verify:

- [ ] APK installs successfully on Android 16+
- [ ] All icons render correctly
- [ ] No resource conflicts with other themes
- [ ] Preview image meets specifications
- [ ] JSON metadata is complete and accurate
- [ ] File naming follows conventions
- [ ] URLs point to correct locations
- [ ] Theme description is clear and helpful
- [ ] Proper attribution for assets

## Code of Conduct

- Be respectful to other contributors
- Provide constructive feedback
- Credit original authors when building upon existing work
- Don't submit copyrighted material without permission

## Questions?

Open an issue on GitHub or contact the AxionAOSP team.

## License

By submitting a theme, you agree that:
- You have the rights to distribute the theme
- The theme can be distributed through AxThemeStore
- You retain copyright of your original work
- Users can freely use the theme on their devices

---

Thank you for contributing to AxionAOSP!
