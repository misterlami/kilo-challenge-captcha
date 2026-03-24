## 1. Project Setup

- [x] 1.1 Create `index.html` with basic HTML5 structure, inline CSS, and inline JS sections
- [x] 1.2 Set up a main game container with sections for: mascot area, waveform display, controls, and score

## 2. Fart Sound Engine

- [x] 2.1 Implement `FartSoundEngine` class with Web Audio API oscillator-based fart synthesis
- [x] 2.2 Create 6 distinct fart sound profiles (squeak, rumble, doubleTap, longTooter, sputter, machineGun) with frequency/envelope/noise configs
- [x] 2.3 Implement sound playback with audio context management
- [x] 2.4 Add `ROUND_CONFIG` array for configurable fart assignment per round

## 3. Microphone Recording

- [x] 3.1 Implement microphone permission request and `getUserMedia` setup
- [x] 3.2 Implement `MicrophoneRecorder` class that captures audio during a timed window
- [x] 3.3 Add volume threshold detection to filter silence/background noise
- [x] 3.4 Handle microphone errors gracefully (denied, unavailable)

## 4. Audio Analysis & Scoring

- [x] 4.1 Implement pitch detection from recorded audio (dominant frequency extraction)
- [x] 4.2 Implement duration measurement from recorded audio
- [x] 4.3 Implement `Scorer` class that compares target vs user input (pitch, duration within tolerances)
- [x] 4.4 Calculate percentage score and determine pass/fail per round

## 5. Mascot Animation

- [x] 5.1 Create CSS-animated butt cheek character with facial expressions
- [x] 5.2 Implement expression progression across rounds
- [x] 5.3 Add demo animation that visually "performs" the target fart sound
- [x] 5.4 Add real-time reaction animation during user recording

## 6. Waveform Visualization

- [x] 6.1 Implement canvas-based waveform renderer for target sound display
- [x] 6.2 Implement live waveform visualization during microphone recording
- [x] 6.3 Add side-by-side comparison view during scoring

## 7. Game Flow & UI

- [x] 7.1 Implement game state machine (idle → demo → recording → scoring → result)
- [x] 7.2 Build round progression logic (2 rounds, 3 tries each, must pass both)
- [x] 7.3 Add phase transition animations and text ("Watch!", "Your Turn!", "Scoring...")
- [x] 7.4 Implement score display with pass/fail feedback per attempt
- [x] 7.5 Implement tries remaining indicator
- [x] 7.6 Build final captcha result screen (pass/fail with humorous summary)
- [x] 7.7 Add "Try Again" reset functionality

## 8. Neobrutalist Theme

- [x] 8.1 Apply neobrutalist CSS — thick black borders (3-4px), bold flat colors, heavy typography
- [x] 8.2 No rounded corners, no soft shadows, raw geometric shapes
- [x] 8.3 High-contrast color palette (yellow, red, blue, white, black)
- [x] 8.4 Add intro screen with absurd "Prove You're Human" copy and start button

## 9. Polish

- [x] 9.1 Test in Chrome and fix any Web Audio API quirks
