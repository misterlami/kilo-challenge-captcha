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
The system SHALL manage two sequential rounds, each with up to three tries.

#### Scenario: Round 1
- **WHEN** round 1 begins
- **THEN** the user must replicate the fart sound(s) assigned to round 1 via `ROUND_CONFIG` (default: single squeak)

#### Scenario: Round 2
- **WHEN** round 2 begins
- **THEN** the user must replicate the fart sound(s) assigned to round 2 via `ROUND_CONFIG` (default: squeak + rumble)

#### Scenario: Round retry
- **WHEN** user fails a round attempt
- **THEN** the system decrements the try counter and allows re-attempt up to 3 total tries

#### Scenario: Tries exhausted
- **WHEN** all 3 tries are used on a round without passing
- **THEN** that round is marked as failed

### Requirement: Fart profile configuration
The system SHALL provide 6 named fart sound profiles that can be assigned to rounds.

#### Scenario: Available profiles
- **WHEN** the `FART_PROFILES` object is defined
- **THEN** it contains 6 profiles: squeak, rumble, doubleTap, longTooter, sputter, machineGun

#### Scenario: Round configuration
- **WHEN** the `ROUND_CONFIG` array is defined
- **THEN** it specifies which fart profiles are used in round 1 and round 2 as a simple array of arrays

### Requirement: Pass/fail determination
The system SHALL determine captcha pass/fail based on round outcomes.

#### Scenario: Pass - both rounds succeeded
- **WHEN** user passes both rounds (within 3 tries each)
- **THEN** captcha result is PASS and a triumphant message is displayed

#### Scenario: Fail
- **WHEN** user fails either round (all 3 tries exhausted)
- **THEN** captcha result is FAIL with a humorous message

### Requirement: Result callback
The system SHALL expose the captcha result for external consumption.

#### Scenario: Result available
- **WHEN** captcha completes
- **THEN** the result (pass/fail, scores per round, tries used) is available via a JavaScript callback or DOM event

#### Scenario: Reset capability
- **WHEN** user wants to retry the entire captcha
- **THEN** a "Try Again" button resets all state and starts fresh
