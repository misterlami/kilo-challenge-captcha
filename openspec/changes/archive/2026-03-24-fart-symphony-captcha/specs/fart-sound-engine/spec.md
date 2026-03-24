## ADDED Requirements

### Requirement: Sound synthesis
The system SHALL synthesize fart sounds using Web Audio API oscillators with configurable pitch, duration, waveform type, and noise blending.

#### Scenario: Single fart sound plays
- **WHEN** the system triggers a fart sound
- **THEN** a low-frequency sawtooth oscillator sound plays with frequency sweep, amplitude envelope (attack-decay), and white noise blending for organic texture

#### Scenario: Six configurable fart types
- **WHEN** the system generates different fart sounds
- **THEN** each sound has distinct characteristics drawn from 6 available profiles (squeak, rumble, doubleTap, longTooter, sputter, machineGun), created by varying frequency range, duration, vibrato, noise mix, and envelope shape

#### Scenario: Fart profiles are swappable via config
- **WHEN** the `ROUND_CONFIG` array is edited
- **THEN** the farts assigned to each round change without modifying synthesis or scoring code

### Requirement: Microphone recording
The system SHALL record user audio input via microphone during a designated capture window.

#### Scenario: Recording starts on prompt
- **WHEN** the system enters the "your turn" phase
- **THEN** microphone capture begins and a visual recording indicator is shown

#### Scenario: Recording stops after timeout
- **WHEN** the recording window expires (configurable, default 5 seconds)
- **THEN** microphone capture stops and audio data is passed to analysis

#### Scenario: No microphone available
- **WHEN** microphone permission is denied or unavailable
- **THEN** the system displays an error message and does not proceed to scoring

### Requirement: Audio analysis
The system SHALL analyze recorded audio to extract pitch, duration, and volume characteristics.

#### Scenario: Pitch detection
- **WHEN** recorded audio is analyzed
- **THEN** the system determines the dominant frequency within ±50 Hz accuracy using autocorrelation

#### Scenario: Duration measurement
- **WHEN** recorded audio is analyzed
- **THEN** the system determines the duration of the sound above the volume threshold

#### Scenario: Silence filtering
- **WHEN** recorded audio contains background noise below the volume threshold
- **THEN** the system ignores that portion and only analyzes sound above the threshold

### Requirement: Scoring
The system SHALL score user input against the target fart sound pattern.

#### Scenario: Pitch match scoring
- **WHEN** user pitch is within ±50 Hz of target pitch
- **THEN** pitch score contributes positively to overall score

#### Scenario: Duration match scoring
- **WHEN** user sound duration is within ±35% of target duration
- **THEN** duration score contributes positively to overall score

#### Scenario: Overall score calculation
- **WHEN** pitch, duration, and rhythm scores are combined
- **THEN** the system produces a percentage score from 0-100%
