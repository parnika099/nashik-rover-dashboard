# Raspberry Pi — Rover detection

Python script for the Nirmalya rover that detects:

- **Obstacles** — ultrasonic (HC-SR04) distance in cm
- **Motion** — camera-based motion area and centroid
- **Colored regions** — orange (e.g. bins/Nirmalya), green (markers) via HSV

## Setup

```bash
cd raspberry-pi
pip install -r requirements.txt
```

On Raspberry Pi, use `opencv-python-headless` and ensure `RPi.GPIO` is installed for the ultrasonic sensor.

## Ultrasonic (optional)

Wire HC-SR04:

- **TRIG** → GPIO 17  
- **ECHO** → GPIO 27  
- **VCC** → 5V  
- **GND** → GND  

If no Pi/GPIO is available, the script still runs and only camera detection is used.

## Run

```bash
python detect.py
```

Use a USB webcam or Pi Camera. Press Ctrl+C to stop.

## Output

- Distance in cm and `[OBSTACLE]` when &lt; 50 cm  
- Motion events (area and center)  
- Count and positions of orange/green regions (e.g. bins)
