# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

This is an IntelliJ IDEA plugin that provides the Spacegray Dark theme, inspired by the Spacegray theme from SublimeText. The plugin offers three theme variants:

- **Primary**: Basic dark theme with same color for UI and editor areas
- **Pro**: Basic dark theme with different colors for UI and editor areas  
- **SE**: Original Spacegray dark blue UI style with different colors for UI and editor areas

## Project Structure

This is a simple IntelliJ plugin project with the following key structure:

```
/
├── resources/                          # Plugin resources
│   ├── META-INF/
│   │   ├── plugin.xml                 # Plugin configuration and metadata
│   │   └── pluginIcon.svg             # Plugin icon
│   └── theme/                         # Theme definitions
│       ├── *.theme.json               # UI theme configurations
│       └── *.xml                      # Editor color schemes
├── out/production/                     # Compiled output
├── screenshots/                       # Theme preview images
└── intellij-spacegray-dark.iml       # IntelliJ module file
```

## Theme Architecture

The plugin uses IntelliJ's theme provider system:

1. **Theme Configuration**: Each theme variant has a corresponding `.theme.json` file that defines UI colors, component styles, and references the editor scheme
2. **Editor Schemes**: XML files (`.xml`) define syntax highlighting colors and editor-specific styling
3. **Plugin Registration**: The `plugin.xml` file registers each theme variant as a `themeProvider` extension

Theme files are organized in pairs:
- `Spacegray_Dark.theme.json` + `Spacegray_Dark.xml` (SE variant)
- `Spacegray_Dark_Primary.theme.json` + `Spacegray_Dark_Primary.xml` (Primary variant)  
- `Spacegray_Dark_Pro.theme.json` + `Spacegray_Dark_Pro.xml` (Pro variant)

## Development

This is a resource-only plugin with no Java code. Development involves:

1. **Theme Modifications**: Edit the `.theme.json` files to adjust UI colors and component styling
2. **Editor Scheme Changes**: Modify the `.xml` files to change syntax highlighting colors
3. **Plugin Configuration**: Update `plugin.xml` for metadata, version, or theme registration changes

## Building and Testing

The plugin uses IntelliJ's standard build system:
- Build artifacts are generated in the `out/production/` directory
- The final plugin JAR (`intellij-spacegray-dark.jar`) is created in the project root
- Testing requires installing the plugin in an IntelliJ IDE instance

## Version Management

Version information is maintained in:
- `plugin.xml` - Contains version number and change notes
- Plugin supports IntelliJ builds since version 191
- Current version: 1.0.6

## Color Palette Reference

The themes use a consistent color palette based on:
- Background colors: `#232830`, `#2b303b` (SE), `#1E1F22`, `#2B2D30` (Primary/Pro)
- Foreground colors: `#A7ADBA`, `#C0C5CE`
- Accent colors: Various grays and blues consistent with Spacegray aesthetic