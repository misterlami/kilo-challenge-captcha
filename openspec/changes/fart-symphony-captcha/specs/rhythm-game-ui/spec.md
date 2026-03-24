## ADDED Requirements

### Requirement: Animated mascot
The system SHALL display an animated butt cheek character that demonstrates each fart sound with facial expressions.

#### Scenario: Pre-round demonstration
- **WHEN** a new round begins
- **THEN** the mascot visually "performs" the target fart sound with appropriate animation (e.g., cheeks puff, facial expression changes)

#### Scenario: Escalating expressions
- **WHEN** rounds progress from 1 to 3
- **THEN** the mascot's facial expressions become increasingly ridiculous — from calm to strained to ecstatic

#### Scenario: User attempt feedback
- **WHEN** the user is performing their fart sound
- **THEN** the mascot reacts in real-time with visual feedback (e.g., watching, encouraging)

### Requirement: Waveform visualization
The system SHALL display a visual waveform for both the target sound and user input.

#### Scenario: Target waveform display
- **WHEN** the target fart sound plays
- **THEN** a waveform visualization shows the sound pattern the user needs to match

#### Scenario: User waveform display
- **WHEN** the user records their input
- **THEN** a live waveform visualization shows the captured audio in real-time

#### Scenario: Side-by-side comparison
- **WHEN** scoring occurs
- **THEN** the target waveform and user waveform are displayed side by side for comparison

### Requirement: Score display
The system SHALL show the user's score with visual feedback after each round.

#### Scenario: Pass feedback
- **WHEN** user scores above the pass threshold (60%)
- **THEN** a celebratory animation plays and the user advances to the next round

#### Scenario: Fail feedback
- **WHEN** user scores below the pass threshold
- **THEN** a humorous "try again" message appears with encouraging text

#### Scenario: Final result
- **WHEN** all three rounds are completed (or failed)
- **THEN** the system displays overall captcha result (pass/fail) with a fun summary

### Requirement: Round progression UI
The system SHALL clearly communicate round status and progression.

#### Scenario: Round indicator
- **WHEN** the user is in a round
- **THEN** the current round number (1, 2, or 3) and total rounds are displayed

#### Scenario: Phase transitions
- **WHEN** the game transitions between demo, recording, and scoring phases
- **THEN** clear visual cues indicate the current phase (e.g., "Watch!", "Your Turn!", "Scoring...")
