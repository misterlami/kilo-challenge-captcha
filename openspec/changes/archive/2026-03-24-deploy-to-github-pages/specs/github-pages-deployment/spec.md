## ADDED Requirements

### Requirement: Site accessible via HTTPS
The GitHub Pages deployment SHALL serve the application over HTTPS.

#### Scenario: HTTPS URL resolves
- **WHEN** user navigates to `https://misterlami.github.io/kilo-challenge-captcha/`
- **THEN** the browser loads the captcha application with a valid TLS certificate

### Requirement: Microphone access works in production
The deployed site SHALL support microphone access via the Web Audio API.

#### Scenario: Microphone prompt appears
- **WHEN** user clicks "Prove I'm Human" on the deployed site
- **THEN** the browser prompts for microphone permission and audio capture works after grant

### Requirement: Auto-deploy on push
GitHub Pages SHALL automatically redeploy when changes are pushed to the `main` branch.

#### Scenario: Push triggers rebuild
- **WHEN** a commit is pushed to `main`
- **THEN** GitHub Pages rebuilds and serves the updated `index.html` within minutes

### Requirement: Full application functionality
The deployed site SHALL retain all features of the local version.

#### Scenario: Complete captcha flow
- **WHEN** user completes the full captcha flow (2 rounds, microphone input, scoring)
- **THEN** all features work identically to the local `file://` version including waveform visualization, mascot animation, and pass/fail scoring
