# Forma

Forma is a minimal native macOS viewer for opening and reading different kinds of content through Apple frameworks.

It is built with Swift and SwiftUI, with native viewers for common formats:

- PDF files through PDFKit
- Web pages through WebKit
- CSV files through an AppKit table view
- Text and Markdown through SwiftUI views
- Images through native image rendering
- System-supported files through Quick Look

## Current Features

- Open files with the native file picker
- Drag and drop local files
- Open web pages from a URL
- Detect file type automatically
- Search PDF, CSV, text, and Markdown content
- Share the opened item from the viewer toolbar
- Show a clear unsupported/error state
- Use native macOS styling, materials, toolbars, and Dark/Light mode behavior

## Build

Forma is a Swift Package Manager macOS app.

```bash
swift build
```

To build and launch the app bundle locally:

```bash
./script/build_and_run.sh
```

To verify the app starts:

```bash
./script/build_and_run.sh --verify
```

## Package a DMG

Create a release-ready DMG locally:

```bash
./script/package_dmg.sh
```

The script builds a release app bundle, applies an ad-hoc signature, creates a DMG with `Forma.app` and an `Applications` shortcut, verifies the image, and writes the final artifact to:

```text
outputs/Forma-0.1.0.dmg
```

Set a custom version with:

```bash
VERSION=0.2.0 ./script/package_dmg.sh
```

The generated DMG is suitable to upload manually to a GitHub Release. For production distribution outside GitHub, sign with a Developer ID certificate and notarize the DMG with Apple.

## Requirements

- macOS 14 or newer
- Swift 6 toolchain

## Project Structure

- `Sources/Forma/App`: app entrypoint
- `Sources/Forma/Models`: content models and format metadata
- `Sources/Forma/Stores`: app state
- `Sources/Forma/Services`: file loading and content detection
- `Sources/Forma/Views`: SwiftUI/AppKit/WebKit/PDFKit viewers
