# Lottie Lower Third Generator

A browser-based tool for creating and previewing animated lower-third overlays as Lottie JSON files. Built for use with ChurchPresenter.

## Features

- Visual editor for lower-third animations (name, info text, logo, borders)
- Live preview with playback controls
- Customizable colors, fonts, sizes, and animation timing
- Preset library — save and reuse configurations
- Color theme system with built-in themes (Classic Red, Ocean Blue, Emerald, etc.)
- Logo upload support (PNG, JPG, SVG, WebP)
- Export to Lottie JSON format
- Light and dark UI themes
- Local webfonts (Open Sans, Roboto, Lato, Montserrat, Nunito, Oswald, Playfair Display, Raleway, Poppins, Source Sans 3)

## Requirements

- [Node.js](https://nodejs.org/) (any recent version)

## Quick Start

**Linux / macOS:**
```bash
./start.sh
```

**Windows:**
```
start.bat
```

This starts a local server on `http://localhost:8090` and opens the generator in your default browser.

### Standalone Mode

You can also open `lottie-generator.html` directly in a browser without running the server. This provides limited functionality — preset saving/loading, color theme persistence, and logo uploads will be unavailable since they rely on the server API.

## Project Structure

```
├── serve.js                 # Node.js HTTP server with REST API
├── lottie-generator.html    # Main application (single-page app)
├── lottie.min.js            # Lottie player library
├── fonts.css                # Local webfont definitions
├── fonts/                   # Webfont files (woff2)
├── logos/                   # Uploaded logo images
├── presets.json             # Saved preset configurations
├── color-themes.json        # Saved color themes
├── start.sh                 # Launch script (Linux/macOS)
└── start.bat                # Launch script (Windows)
```

## API Endpoints

| Method | Endpoint            | Description             |
|--------|---------------------|-------------------------|
| GET    | `/api/presets`      | List saved presets      |
| POST   | `/api/presets`      | Save presets            |
| GET    | `/api/color-themes` | List saved color themes |
| POST   | `/api/color-themes` | Save color themes       |
| GET    | `/api/logos`        | List uploaded logos     |
| POST   | `/api/logos`        | Upload a logo (base64)  |
