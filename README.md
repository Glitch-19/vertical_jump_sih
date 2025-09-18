# Vertical Jump Measurement System

A computer-vision program that measures an athlete's vertical jump and prevents common cheating methods. Built with OpenCV and MediaPipe.

## 1) Core Purpose and Technology

- Purpose: Measure the explosive power of an athlete's full body, particularly the lower limbs, which is critical for performance on and off the field, track, or court.
- Technology Used: OpenCV and MediaPipe.

## 2) Body Landmark Mapping

- The program maps body landmarks using bluish-purple dots and connecting lines.
- Facial landmarks are also identified; the nose is especially important for user interaction.

## 3) Program Interaction and Control Logic

- Initiate a Jump Measurement: Tap the right hand to the nose to put the system into “ready to measure” mode.
- Reset/Retry a Jump: After receiving a measurement, tap the left hand to the nose to reset and redo the test.
- Demonstration Flow: The system can measure multiple jumps in sequence (e.g., small, medium, large). For example, after a ~4-inch jump, the user taps left hand to reset, then right hand to initiate the next jump.

## 4) Vertical Jump Measurement

- The system measures the athlete’s vertical jump and reports the result in inches.
- During a jump, the program tracks states (e.g., “Airborne Landing”) and produces a measurement, such as “31 and a half inches.”
- The program is able to reliably estimate vertical jump height.

## 5) Anti-Cheat Feature Logic

- Problem with Traditional Methods: Vertical jump mats can be exploited by bringing knees up and squatting on landing to prolong perceived hang time, inflating the measured jump.
- Detection Mechanism: The program detects a “squatted landing” or “cheating jump” by analyzing ankle, knee, and hip alignment indicative of squatting.
- Program Reaction:
	- Valid Jump: A valid measurement is displayed.
	- Cheating Detected: The measurement is canceled and a “bad attempt” notification is shown.
	- Retry: After a “bad attempt,” the user can redo the test.

## Effectiveness

This anti-cheat feature enables the system to detect landing exploits commonly seen in traditional vertical jump tests, helping ensure accurate and trustworthy measurements.

## Quick Start (Windows)

1) Activate the existing virtual environment and install dependencies.

2) Run the app and allow camera access.

### Commands (Windows CMD)

Optional: if not already active, activate your venv and install requirements, then run:

```
pip install -r requirements.txt
python src\main.py
```

## Controls

- Right hand to nose: Arm/start measurement
- Left hand to nose: Reset/retry
- q or Esc: Quit

## Calibration

Configure these variables in `.env`:

- `CALIBRATION_INCHES` (default 12)
- `CALIBRATION_PIXELS` (default 100)
- `MIN_JUMP_INCHES` (default 2.0)
- `SMOOTHING_WINDOW` (default 5)

Inches = pixels × (CALIBRATION_INCHES / CALIBRATION_PIXELS)


