# Real-Time Eye Drowsiness Detection System

A deep learning application that uses computer vision to monitor a driver's eyes in real-time and trigger an alert if signs of drowsiness are detected. This project was developed in the PyCharm IDE.

---

## Table of Contents

- [Project Overview](#project-overview)
- [How It Works](#how-it-works)
- [Core Features](#core-features)
- [Technology Stack](#technology-stack)
- [Prerequisites](#prerequisites)
- [Installation and Setup](#installation-and-setup)
- [Running the Application](#running-the-application)
- [Project Structure](#project-structure)

---

## Project Overview

Driver fatigue is a significant cause of traffic accidents. This project aims to provide a solution by creating an automated system that can detect driver drowsiness and prevent potential accidents. The application uses a standard webcam to capture the video feed of the driver, detects the face, focuses on the eyes, and analyzes the eye state to determine if the person is feeling sleepy.

---

## How It Works

The system operates through a multi-stage pipeline:

1.  **Video Capture**: Accesses the webcam to get a live video stream.
2.  **Face Detection**: In each frame, it detects the presence of a human face using a pre-trained face detector.
3.  **Facial Landmark Detection**: Once a face is detected, it identifies key facial landmarks (for the eyes, nose, mouth, etc.). This is crucial for isolating the eye regions.
4.  **Eye State Analysis**: The system calculates the Eye Aspect Ratio (EAR), a value that is nearly constant when an eye is open but drops to zero when it is closed.
5.  **Drowsiness Detection**: If the EAR remains below a certain threshold for a specific number of consecutive frames, the system concludes that the person is drowsy.
6.  **Alert System**: Upon detecting drowsiness, an alarm is triggered to alert the driver.

---

## Core Features

-   **Real-Time Monitoring**: Processes live video feed directly from a webcam with minimal latency.
-   **High-Accuracy Detection**: Utilizes established computer vision libraries for robust face and landmark detection.
-   **Non-Intrusive**: Works with any standard webcam without requiring special hardware.
-   **Audible Alarm**: Plays a sound to alert the user immediately when drowsiness is detected.

---

## Technology Stack

-   **Programming Language**: Python
-   **Core Libraries**:
    -   **OpenCV**: For real-time video capture and image processing.
    -   **Dlib**: For high-performance face detection and facial landmark prediction.
    -   **SciPy**: For spatial calculations needed for the Eye Aspect Ratio.
    -   **Pygame**: For playing the alarm sound.

---

## Prerequisites

Ensure you have the following software installed on your local machine:

-   [Python](https://www.python.org/downloads/) (v3.7 or higher recommended)
-   [pip](https://pip.pypa.io/en/stable/installation/) (comes with Python)
-   [CMake](https://cmake.org/download/) (required for Dlib installation on some systems)
-   [Git](https://git-scm.com/downloads/)

---

## Installation and Setup

Follow these instructions to get the project running.

### 1. Clone the Repository

```bash
git clone [https://github.com/nivas25/Eye_drowsiness_detection.git](https://github.com/nivas25/Eye_drowsiness_detection.git)
cd Eye_drowsiness_detection
```

### 2. Set Up a Python Virtual Environment

Using a virtual environment is highly recommended to avoid conflicts with other projects.

```bash
# Create a virtual environment
python -m venv venv

# Activate the virtual environment
# On Windows:
venv\Scripts\activate
# On macOS/Linux:
source venv/bin/activate
```

### 3. Install Dependencies

Install all the required Python packages from the `requirements.txt` file.

```bash
pip install -r requirements.txt
```
*Note: Installing `dlib` can sometimes be complex. If you encounter issues, please refer to the official dlib documentation for platform-specific installation guides.*

### 4. Download Pre-trained Model

This project requires a pre-trained facial landmark predictor model from Dlib.

-   Download the model file: `shape_predictor_68_face_landmarks.dat.bz2` from the [Dlib website](http://dlib.net/files/shape_predictor_68_face_landmarks.dat.bz2).
-   Extract the `.dat` file from the downloaded archive.
-   Place the `shape_predictor_68_face_landmarks.dat` file in the project's root directory or a designated `models` folder.

---

## Running the Application

Once the setup is complete, you can run the drowsiness detection script.

1.  Make sure your virtual environment is activated.
2.  Ensure your webcam is connected and accessible.
3.  Execute the main Python script.

    ```bash
    # Replace 'detect_drowsiness.py' with the actual name of your main script
    python detect_drowsiness.py
    ```

4.  A window will appear showing your webcam feed with facial landmarks drawn on it. To stop the application, press the `q` key.

---

## Project Structure

A brief overview of the key files in this project:

```
Eye_drowsiness_detection/
├── detect_drowsiness.py              # Main script to run the application.
├── shape_predictor_68_face_landmarks.dat # Dlib's pre-trained landmark model.
├── alarm.wav                         # Audio file for the alarm sound.
└── requirements.txt                  # List of Python packages required for the project.
