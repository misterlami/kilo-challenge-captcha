## ADDED Requirements

### Requirement: Animated mascot
The system SHALL display an animated butt cheek character that demonstrates each fart sound with facial expressions.

#### Scenario: Pre-round demonstration
- **WHEN** a new round begins
- **THEN** the mascot visually "performs" the target fart sound with appropriate animation (e.g., cheeks vibrate, facial expression changes)

#### Scenario: Expression progression
- **WHEN** rounds progress from 1 to 2
- **THEN** the mascot's facial expressions escalate from calm to intense

#### Scenario: User attempt feedback
- **WHEN** the user is performing their fart sound
- **THEN** the mascot reacts in real-time with visual feedback (e.g., watching with anticipation)

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
The system SHALL show the user's score with visual feedback after each attempt.

#### Scenario: Pass feedback
- **WHEN** user scores above the pass threshold (40%)
- **THEN** a celebratory animation plays and the user advances to the next round or wins

#### Scenario: Fail feedback
- **WHEN** user scores below the pass threshold
- **THEN** a humorous message appears with encouraging text and the try counter decreases

#### Scenario: Final result
- **WHEN** both rounds are completed (passed or all tries exhausted)
- **THEN** the system displays overall captcha result (pass/fail) with a fun summary

### Requirement: Round progression UI
The system SHALL clearly communicate round status, tries remaining, and progression.

#### Scenario: Round indicator
- **WHEN** the user is in a round
- **THEN** the current round number (1 or 2) and total rounds are displayed

#### Scenario: Tries indicator
- **WHEN** the user is attempting a round
- **THEN** the number of remaining tries (out of 3) is displayed

#### Scenario: Phase transitions
- **WHEN** the game transitions between demo, recording, and scoring phases
- **THEN** clear visual cues indicate the current phase (e.g., "Watch!", "Your Turn!", "Scoring...")

### Requirement: Neobrutalist theme
The system SHALL use a neobrutalist visual style throughout all UI elements.

#### Scenario: Styling characteristics
- **WHEN** the page renders
- **THEN** all elements use thick black borders (3-4px), bold flat background colors, heavy typography, no rounded corners, no soft shadows, and raw geometric shapes

#### Scenario: Color palette
- **WHEN** UI elements are displayed
- **THEN** the color palette uses high-contrast combinations (bright yellow, red, blue, white, black) with no gradients
