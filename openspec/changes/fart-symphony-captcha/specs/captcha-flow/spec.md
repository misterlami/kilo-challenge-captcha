## ADDED Requirements

### Requirement: Captcha entry point
The system SHALL present a captcha entry screen that initiates the fart symphony experience.

#### Scenario: Start captcha
- **WHEN** user arrives at the page
- **THEN** a "Prove You're Human" button is displayed with absurd copy explaining the challenge

#### Scenario: Microphone permission
- **WHEN** user clicks start
- **THEN** the system requests microphone permission before proceeding

### Requirement: Round management
The system SHALL manage three sequential rounds of increasing difficulty.

#### Scenario: Round 1 - Simple fart
- **WHEN** round 1 begins
- **THEN** the user must replicate a single simple fart sound (one pitch, short duration)

#### Scenario: Round 2 - Double fart
- **WHEN** round 2 begins
- **THEN** the user must replicate two fart sounds with different pitches

#### Scenario: Round 3 - Fart pattern
- **WHEN** round 3 begins
- **THEN** the user must replicate a three-fart pattern with rhythm and pitch variation

#### Scenario: Round retry
- **WHEN** user fails a round
- **THEN** the system allows one retry before marking that round as failed

### Requirement: Pass/fail determination
The system SHALL determine captcha pass/fail based on round outcomes.

#### Scenario: Pass - all rounds succeeded
- **WHEN** user passes all three rounds
- **THEN** captcha result is PASS and a triumphant message is displayed

#### Scenario: Pass - majority succeeded
- **WHEN** user passes at least 2 of 3 rounds
- **THEN** captcha result is PASS (generous threshold)

#### Scenario: Fail
- **WHEN** user fails 2 or more rounds
- **THEN** captcha result is FAIL with a humorous message

### Requirement: Result callback
The system SHALL expose the captcha result for external consumption.

#### Scenario: Result available
- **WHEN** captcha completes
- **THEN** the result (pass/fail, scores per round) is available via a JavaScript callback or DOM event

#### Scenario: Reset capability
- **WHEN** user wants to retry the entire captcha
- **THEN** a "Try Again" button resets all state and starts fresh
