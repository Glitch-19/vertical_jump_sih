# Run and Calibrate

## Setup

1. Activate your virtual environment (already present at `myenv`), then install dependencies.
2. Run the app and allow camera permission.

## Controls

- Right hand to nose: Arm/start measurement
- Left hand to nose: Reset/retry
- q or Esc: Quit

## Calibration

Use `.env` to set:
- `CALIBRATION_INCHES` (default 12)
- `CALIBRATION_PIXELS` (default 100)
- `MIN_JUMP_INCHES` (default 2.0)

Inches = pixels * (CALIBRATION_INCHES / CALIBRATION_PIXELS)

## Install deps (Windows CMD)

pip install -r requirements.txt

## Run

python src\main.py
