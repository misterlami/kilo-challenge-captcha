## Why

The Fart Symphony Conductor captcha is a single self-contained `index.html` file currently only accessible locally. Deploying it to GitHub Pages makes it publicly accessible at a permanent URL for demo, testing, and submission purposes — at zero cost and with minimal setup.

## What Changes

- Enable GitHub Pages on the existing `misterlami/kilo-challenge-captcha` repository
- Serve the `index.html` file from the `main` branch root directory
- No code changes required — the existing HTML file is already fully self-contained with inline CSS and JS

## Capabilities

### New Capabilities
- `github-pages-deployment`: Hosting the captcha app on GitHub Pages with HTTPS support

### Modified Capabilities
(none)

## Impact

- **GitHub Settings**: One-time configuration change in repo Settings > Pages
- **No code changes**: `index.html` is already a standalone static file
- **URL**: Site will be available at `https://misterlami.github.io/kilo-challenge-captcha/`
- **HTTPS**: Provided automatically by GitHub Pages (required for `getUserMedia` microphone access)
- **No build step**: GitHub Pages serves files directly from the repository
