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
