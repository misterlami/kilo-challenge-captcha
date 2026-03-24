# Fart Symphony Conductor — Kilo Worst Captcha Challenge

An absurd captcha that forces users to replicate fart sounds into their microphone to prove they're human.

## How It Works

1. A fart sound plays (synthesized via Web Audio API)
2. You replicate it into your mic — pitch, duration, and tone all count
3. Two rounds, three tries each. Pass both or get labeled a robot.

## Features

- 6 configurable fart sound profiles (squeak, rumble, doubleTap, longTooter, sputter, machineGun)
- Real-time waveform visualization of target vs. your input
- Animated mascot that reacts to your performance
- Neobrutalist UI — thick black borders, bold flat colors, no rounded corners
- Microphone-based pitch detection via autocorrelation
- 40% pass threshold per round

## Usage

Open `index.html` in Chrome. Microphone required.

## Configuration

All config is at the top of the `<script>` block in `index.html`. Search for `const <variable>` to find each:

| Variable | Default | Description |
|----------|---------|-------------|
| `PASS_THRESHOLD` | `40` | Minimum score to pass a round |
| `TOTAL_ROUNDS` | `2` | Number of rounds |
| `MAX_TRIES` | `3` | Attempts per round |
| `RECORDING_DURATION` | `5000` | Mic capture window in ms |
| `ROUND_CONFIG` | see below | Which fart profiles each round uses |
| `FART_PROFILES` | 6 entries | All sound definitions (freq, duration, noise, etc.) |

### Swapping Farts

Edit `ROUND_CONFIG` to pick which farts appear in each round:

```js
const ROUND_CONFIG = [
  ['squeak'],                    // Round 1
  ['doubleTap', 'longTooter'],   // Round 2
];
```

Available profiles: `squeak`, `rumble`, `doubleTap`, `longTooter`, `sputter`, `machineGun`

### Adding a Round

1. Add an entry to `ROUND_CONFIG`
2. Increment `TOTAL_ROUNDS`
3. Add a mascot expression and label to `MASCOT_EXPR` and `MASCOT_LABELS`

## Challenge Rules

- Must use Xiaomi Mimo-V2 Pro or Mimo-V2 Omni model
- Submit by **Wed, Mar 25th 11:59 pm PST**: [Submit Here](https://form.typeform.com/to/UKcncLSw)

## Prizes

| Place | Prize                           |
| ----- | ------------------------------- |
| 1st   | $250 Amazon + $500 Kilo Credits |
| 2nd   | $250 Kilo Credits               |
| 3rd   | $150 Kilo Credits               |

## Tech

Single HTML file. No frameworks, no build tools, no dependencies. Pure Web Audio API + CSS animations.
