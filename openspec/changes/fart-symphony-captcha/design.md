## Context

The Kilo Worst Captcha Challenge requires building an absurd captcha using vanilla HTML/CSS/JS with no frameworks. The project must use the Xiaomi Mimo-V2 Pro or Mimo-V2 Omni model and be submitted by Wed, Mar 25th 11:59 pm PST. The entire solution runs client-side in the browser — no server, no backend, no build tools.

## Goals / Non-Goals

**Goals:**
- Build a hilarious, functional captcha in a single HTML file (plus optional CSS/JS)
- Use Web Audio API to synthesize fart sounds and detect microphone input
- Create an engaging rhythm game with clear visual feedback
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
**Decision**: Use Web Audio API's `OscillatorNode` + `GainNode` to synthesize fart sounds, and `MediaRecorder` / `AudioContext.createMediaStreamSource` for microphone input.
**Alternatives considered**: Pre-recorded audio files (rejected — less fun, more assets), Tone.js (rejected — adds dependency).
**Rationale**: Pure browser API, no dependencies. Fart sounds are easy to synthesize with low-frequency oscillators and envelope shaping.

### Rhythm game scoring approach
**Decision**: Compare user input waveform against target waveform using pitch correlation and duration matching within tolerance thresholds.
**Rationale**: Simple to implement, visually demonstrable, forgiving enough for a captcha. We compare:
- **Pitch**: Dominant frequency match within ±50 Hz
- **Duration**: Sound length within ±30%
- **Timing**: Sequence of sounds matches count

### Three-round escalating difficulty
**Decision**: Round 1 = one simple fart, Round 2 = two farts with different pitches, Round 3 = three-fart pattern with rhythm.
**Rationale**: Teaches the mechanic progressively, gives judges escalating absurdity. Round 3 is the "boss fight."

## Risks / Trade-offs

**[Mic input noise]** → Implement a noise gate: only capture audio above a volume threshold. Show a "recording" indicator so user knows when to perform.

**[Browser compatibility]** → Web Audio API is well-supported in Chrome/Edge/Firefox. Add a mic permission prompt at start. Graceful error if mic not available.

**[Scoring too strict/too loose]** → Default to generous thresholds (60% match = pass). This is a captcha, not a music exam. Can tune based on testing.

**[Fart sounds sound bad]** → That's the point. But seriously — use frequency sweeps (200-80 Hz) with amplitude modulation to create realistic-ish sounds. Multiple waveforms (sawtooth, square) for variety.

## Migration Plan

N/A — greenfield project. No existing code to migrate.
