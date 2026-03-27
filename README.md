# AirCanvas ✋🖌️

AirCanvas is a **gesture-based drawing app**: it turns your hand into a virtual stylus using MediaPipe Hands and OpenCV, so you can draw in the air by pinching your thumb and index finger together. This is the **BUILDCORED ORCAS — Day 02** project.

## How it works

- Uses OpenCV to read frames from your webcam in real time.  
- Uses MediaPipe Hands to detect 21 hand landmarks and track the **thumb tip** and **index tip**.
- Computes the distance between thumb and index; when that distance is **below a threshold**, it treats it as a **pinch** and draws on a persistent canvas.  
- Draws smooth strokes by connecting the fingertip position across frames and overlays the canvas on top of the live video feed.

## Requirements

- Python 3.10.x  
- A working webcam  

## Python packages

```bash
pip install mediapipe==0.10.13 opencv-python numpy
```

(Use a MediaPipe version that supports mp.solutions.hands for your Python version.)

## Setup
Clone this repository or download the script as aircanvas.py.

Make sure your webcam is connected and not used by other apps.

Install the required Python packages (see above).

## Usage
From the project folder, run:

```bash
aircanvas.py
```

You’ll see a webcam window titled “AirCanvas - Day 02” with:

 - A mirrored camera view.
 - A hand skeleton overlay from MediaPipe.
 - A colored dot on your index fingertip (your drawing cursor).
 - On-screen status and information:
 - Distance between thumb and index (in pixels).
 - Threshold (pinch trigger distance).
 - DRAWING / NOT DRAWING.
 - Current Color name at the bottom.

## Controls

 - Pinch (thumb + index close): draw on the canvas.
 - Unpinch (fingers apart): stop drawing.
 - Number keys 1–9: switch drawing color (mapped to the COLORS list).
 - c: clear the canvas.
 - q: quit and close the window.
 - Tuning the pinch threshold

Credits
Hand tracking: MediaPipe Hands.

Video capture and rendering: OpenCV.

Array operations and canvas storage: NumPy.

Built as part of the BUILDCORED ORCAS — Day 02: AirCanvas challenge.
