## 1. Project Setup

- [ ] 1.1 Create `index.html` with basic HTML5 structure, inline CSS, and inline JS sections
- [ ] 1.2 Set up a main game container with sections for: mascot area, waveform display, controls, and score

## 2. Fart Sound Engine

- [ ] 2.1 Implement `FartSoundEngine` class with Web Audio API oscillator-based fart synthesis
- [ ] 2.2 Create 3 distinct fart sound profiles (squeak, rumble, machine gun) with frequency/envelope configs
- [ ] 2.3 Implement sound playback with audio context management

## 3. Microphone Recording

- [ ] 3.1 Implement microphone permission request and `getUserMedia` setup
- [ ] 3.2 Implement `MicrophoneRecorder` class that captures audio during a timed window
- [ ] 3.3 Add volume threshold detection to filter silence/background noise
- [ ] 3.4 Handle microphone errors gracefully (denied, unavailable)

## 4. Audio Analysis & Scoring

- [ ] 4.1 Implement pitch detection from recorded audio (dominant frequency extraction)
- [ ] 4.2 Implement duration measurement from recorded audio
- [ ] 4.3 Implement `Scorer` class that compares target vs user input (pitch, duration within tolerances)
- [ ] 4.4 Calculate percentage score and determine pass/fail per round

## 5. Mascot Animation

- [ ] 5.1 Create CSS-animated butt cheek character with facial expressions
- [ ] 6.2 Implement expression progression across rounds (calm → strained → ecstatic)
- [ ] 6.3 Add demo animation that visually "performs" the target fart sound
- [ ] 6.4 Add real-time reaction animation during user recording

## 6. Waveform Visualization

- [ ] 6.1 Implement canvas-based waveform renderer for target sound display
- [ ] 6.2 Implement live waveform visualization during microphone recording
- [ ] 6.3 Add side-by-side comparison view during scoring

## 7. Game Flow & UI

- [ ] 7.1 Implement game state machine (idle → demo → recording → scoring → result)
- [ ] 7.2 Build round progression logic (3 rounds, retry on fail)
- [ ] 7.3 Add phase transition animations and text ("Watch!", "Your Turn!", "Scoring...")
- [ ] 7.4 Implement score display with pass/fail feedback per round
- [ ] 7.5 Build final captcha result screen (pass/fail with humorous summary)
- [ ] 7.6 Add "Try Again" reset functionality

## 8. Polish

- [ ] 8.1 Add intro screen with absurd "Prove You're Human" copy and start button
- [ ] 8.2 Add sound effects for UI interactions (button clicks, pass/fail)
- [ ] 8.3 Style everything with CSS — fun colors, animations, ridiculous typography
- [ ] 8.4 Test in Chrome and fix any Web Audio API quirks
