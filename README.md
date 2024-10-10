# Eye Drowsiness Detection

This project implements an AI-based drowsiness detection system using computer vision and a pre-trained facial landmark detector. The system monitors eye movements in real time and triggers an alert when drowsiness is detected, ensuring safety in scenarios such as driving.

## Table of Contents

- [Features](#features)
- [Installation](#installation)
- [Usage](#usage)
- [Code](#code)
- [How It Works](#how-it-works)
- [Requirements](#requirements)
- [Contributing](#contributing)
- [License](#license)

## Features

- **Real-Time Eye Tracking**: Uses a webcam to track eye movements.
- **Drowsiness Detection**: Analyzes the Eye Aspect Ratio (EAR) to detect drowsiness.
- **Audio Alert**: Triggers an audio alert when the user's eyes are closed for a specified duration.
- **User-Friendly Interface**: Displays real-time video feed with detected facial landmarks.

## Installation

1. Clone the repository:
   ```bash
   git clone https://github.com/yourusername/eye_drowsiness_detection.git
   cd eye_drowsiness_detection

Download the required facial landmark predictor file from here and extract the .dat file to the project directory.

2. Usage
To start the drowsiness detection system, run the following command:

```bash
python detect_drowsiness.py --shape-predictor shape_predictor_68_face_landmarks.dat
```

The script will start the webcam and analyze the eye aspect ratio in real time.
An alert will be triggered if drowsiness is detected.

3. How It Works
Eye Aspect Ratio (EAR): The system calculates the EAR using specific facial landmarks around the eyes. If the ratio falls below a threshold for a certain number of consecutive frames, it determines that the user is drowsy.

Facial Landmark Detection: The system uses the dlib library's pre-trained 68-point facial landmark predictor to detect facial landmarks.

Alert System: If the system detects drowsiness, it will display a warning on the video feed and trigger an audio alert using pyttsx3.

4. Requirements
Python 3.x
OpenCV
imutils
dlib
pyttsx3
Webcam for real-time video feed
You can install the dependencies by running:

5. License
This project is licensed under the MIT License. See the LICENSE file for more details.
