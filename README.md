# MYORYX Scan
Editable camera scanner and image-to-PDF web app. All document processing runs locally in the browser; there is no backend or paid API.

## Features
Camera capture with phone-camera fallback; multiple image upload; crop; rotate; grayscale and black-and-white filters; brightness; page ordering; PDF download and supported device sharing; Arabic/English interface.

## Edit
- `public/index.html`: layout, labels, styling
- `public/app.js`: scanner, editing, translations, PDF generation
- `public/manifest.json`: app name and install settings
- `public/icon.svg`: app icon
- `public/sw.js`: basic offline cache (bump cache version when changing assets)

## Local preview
Run `python -m http.server 8000 --directory public`, then open http://localhost:8000. Camera access requires HTTPS or localhost. Accessing a development computer through an ordinary HTTP LAN address will not enable camera access.

## GitHub
Create a repository named `MYORYX-Scan`. Upload the contents of this project folder at the repository root, keeping the `public` folder intact.

## Render
Create a **Static Site**, connect the GitHub repository, leave the build command blank, and set publish directory to `public`. A `render.yaml` is also included for Blueprint deployment. HTTPS enables phone camera access.

## Vercel
Import the repository. Framework: Other. No build command. Output directory: `public`.

## Android
Open the HTTPS website in Chrome. Use Add to home screen when available. This source is a web app, not an APK. A native Android package can be added later.

## Current limitations
Manual rectangular cropping; no automatic page-edge detection, perspective correction, OCR, or searchable text. Images are resized to a maximum dimension of 2200 pixels. Pages are kept in memory and lost when the app reloads. Save the PDF before closing. Camera, device sharing, and home-screen installation require testing on the target phone. Offline use depends on successful initial caching and host access requirements.

## Validation
JavaScript syntax checked. Generated two-page PDF opened successfully with a PDF parser, with embedded JPEGs and A4 dimensions.
