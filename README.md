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

## Requirements

- macOS 14 or newer
- Swift 6 toolchain

## Project Structure

- `Sources/Forma/App`: app entrypoint
- `Sources/Forma/Models`: content models and format metadata
- `Sources/Forma/Stores`: app state
- `Sources/Forma/Services`: file loading and content detection
- `Sources/Forma/Views`: SwiftUI/AppKit/WebKit/PDFKit viewers
