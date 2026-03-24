## Context

The Kilo Worst Captcha Challenge requires building an absurd captcha using vanilla HTML/CSS/JS with no frameworks. The project must use the Xiaomi Mimo-V2 Pro or Mimo-V2 Omni model and be submitted by Wed, Mar 25th 11:59 pm PST. The entire solution runs client-side in the browser — no server, no backend, no build tools.

## Goals / Non-Goals

**Goals:**
- Build a hilarious, functional captcha in a single HTML file (plus optional CSS/JS)
- Use Web Audio API to synthesize fart sounds and detect microphone input
- Create an engaging rhythm game with clear visual feedback
- Neobrutalist visual theme — thick black borders, bold flat colors, heavy typography, raw shapes
- Keep it dead simple — static files, open in browser, done

**Non-Goals:**
- Production-grade audio processing (generous thresholds are fine)
- Accessibility (this is a hackathon challenge, not a product)
- Mobile support (desktop browser only)
- Server-side anything

## Decisions

### Single HTML file vs. multiple files
**Decision**: Single `index.html` with inline CSS and JS.
**Rationale**: Simpler to submit, no build step, everything in one place. Judges can just open it.

### Web Audio API for synthesis and recording
**Decision**: Use Web Audio API's `OscillatorNode` + `GainNode` to synthesize fart sounds, and `getUserMedia` / `ScriptProcessor` for microphone input and waveform capture.
**Alternatives considered**: Pre-recorded audio files (rejected — less fun, more assets), Tone.js (rejected — adds dependency).
**Rationale**: Pure browser API, no dependencies. Fart sounds are synthesized with low-frequency sawtooth oscillators, frequency sweeps, amplitude envelopes, and white noise blending for organic texture.

### Configurable fart sound profiles
**Decision**: Provide 6 named fart profiles in a `FART_PROFILES` config object. Round definitions reference profiles by name via a `ROUND_CONFIG` array of arrays.
**Profiles**: squeak, rumble, doubleTap, longTooter, sputter, machineGun
**Default rounds**: Round 1 = squeak, Round 2 = squeak + rumble.
**Rationale**: Swapping farts is a one-line change in `ROUND_CONFIG`. Judges and testers can experiment without touching synthesis code.

### Two rounds with three tries each
**Decision**: 2 rounds total. Each round allows up to 3 attempts. User must pass both rounds to clear the captcha.
**Rationale**: Fewer rounds = faster experience for judges. 3 tries per round gives users a fair chance to learn the mechanics. Passing both rounds is more decisive than a majority-pass rule.

### Rhythm game scoring approach
**Decision**: Compare user input waveform against target waveform using pitch correlation and duration matching within tolerance thresholds.
**Rationale**: Simple to implement, visually demonstrable, forgiving enough for a captcha. We compare:
- **Pitch**: Dominant frequency match within ±50 Hz
- **Duration**: Sound length within ±35%
- **Timing**: Sequence of sounds matches count

### Neobrutalist visual theme
**Decision**: CSS styled with neobrutalist principles — thick black borders (3-4px), bold flat background colors (yellow, red, blue, white), heavy monospace or bold typography, no rounded corners or soft shadows, raw geometric shapes.
**Rationale**: Visually distinctive, highly legible, and intentionally "ugly" in a funny way that matches the absurdity of the content. Stands out from typical polished captcha UIs.

## Risks / Trade-offs

**[Mic input noise]** → Implement a noise gate: only capture audio above a volume threshold. Show a "recording" indicator so user knows when to perform.

**[Browser compatibility]** → Web Audio API is well-supported in Chrome/Edge/Firefox. Add a mic permission prompt at start. Graceful error if mic not available.

**[Scoring too strict/too loose]** → Default to generous thresholds (40% match = pass). This is a captcha, not a music exam. Can tune based on testing.

**[Fart sounds sound bad]** → That's the point. But seriously — use frequency sweeps with sawtooth oscillators, amplitude modulation, and white noise blending to create organic-sounding farts. Six distinct profiles provide variety.

## Migration Plan

N/A — greenfield project. No existing code to migrate.
