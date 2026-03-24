## Why

The Kilo Worst Captcha Challenge asks participants to build the most absurd possible captcha system. We propose "Fart Symphony Conductor" — an interactive rhythm game where users must replicate fart sound patterns via microphone to prove they're human. The absurdity, visual humor (animated butt cheeks with escalating facial expressions), and clear pass/fail logic make it both technically feasible and competitively strong.

## What Changes

- Build a complete single-page HTML/CSS/JS captcha experience
- Generate synthesized fart sound patterns using Web Audio API
- Record user microphone input and detect pitch, duration, and rhythm matches
- Render an animated rhythm game UI with visual waveform feedback
- Neobrutalist visual theme — thick black borders, bold flat colors, heavy typography, raw shapes
- Two rounds with three tries each — user must pass both rounds to clear the captcha
- Six configurable fart sound types — pick which farts appear in each round via a config variable

## Capabilities

### New Capabilities

- `fart-sound-engine`: Web Audio API synthesis and microphone recording — generates fart sound patterns, records user input, performs pitch/duration/rhythm analysis for scoring. Supports 6 configurable fart types (squeak, rumble, doubleTap, longTooter, sputter, machineGun).
- `rhythm-game-ui`: Visual game interface — animated butt cheeks, waveform display, rhythm indicators, score feedback, round progression, neobrutalist styling
- `captcha-flow`: Captcha verification logic — manages 2 game rounds with 3 tries each, scoring thresholds, pass/fail determination, and result display

### Modified Capabilities

(None — greenfield project)

## Impact

- **Technology**: Vanilla HTML, CSS, JavaScript — no frameworks, no build tools
- **APIs**: Web Audio API for sound synthesis and microphone input
- **Dependencies**: None — pure browser-based solution
- **Deployment**: Static files, can be served from any host or opened directly in browser
- **Deadline**: Must be submitted by Wed, Mar 25th 11:59 pm PST
