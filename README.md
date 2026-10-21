# Face Emotion Detection Using Python

A real-time facial emotion detection project using Python, OpenCV, and the FER (Facial Expression Recognition) library.

## Overview

This project captures live video from a webcam, detects faces, and predicts the dominant facial expression for each detected face.

A green rectangle is drawn around each face, and the predicted emotion and its score are displayed on the video.

## Features

- Real-time webcam video capture
- Face detection and emotion prediction
- Green bounding boxes around detected faces
- Emotion labels with confidence scores
- Support for multiple faces in a frame
- Press `q` to exit the application

## Technologies Used

- Python
- OpenCV
- FER (Facial Expression Recognition)
- TensorFlow (installed as a dependency)

## Supported Emotion Labels

The model can predict seven expression categories:

- Angry
- Disgust
- Fear
- Happy
- Sad
- Surprise
- Neutral

## Project Structure

```text
Face-Emotion-Detection/
├── main.py
├── requirements.txt
└── README.md
```

## Requirements

- Python 3.10, 3.11, or 3.12 recommended
- A working webcam
- Internet access for installing dependencies
- A desktop environment that supports GUI windows

## Installation

### 1. Create and enter the project folder

If you already have the project folder, open a terminal in it. Otherwise:

```bash
mkdir Face-Emotion-Detection
cd Face-Emotion-Detection
```

### 2. Create a virtual environment

```bash
python -m venv .venv
```

### 3. Activate the environment

**Windows Command Prompt:**

```bat
.venv\Scripts\activate
```

**Windows PowerShell:**

```powershell
.\.venv\Scripts\Activate.ps1
```

**Linux or macOS:**

```bash
source .venv/bin/activate
```

### 4. Install dependencies

```bash
python -m pip install --upgrade pip
python -m pip install -r requirements.txt
```

## Run the Application

Run this command from the project folder:

```bash
python main.py
```

The webcam window should open and show detected faces with their predicted expressions. Press **q** to stop the program.

## How It Works

1. OpenCV connects to the computer's webcam.
2. The application continuously reads video frames.
3. FER analyzes each frame to detect faces and estimate facial expressions.
4. The application selects the emotion with the highest model score.
5. OpenCV draws a rectangle around each detected face.
6. The predicted emotion and its score are displayed on the frame.
7. When the user presses `q`, the webcam is released and the application closes.

## Troubleshooting

### Webcam does not open

- Check that the webcam is connected.
- Close other applications that may be using the camera.
- Allow camera access in your operating system's privacy settings.
- If needed, try changing `cv2.VideoCapture(0)` to `cv2.VideoCapture(1)` in `main.py`.

### `ModuleNotFoundError`

Activate the virtual environment and install the dependencies:

```bash
python -m pip install -r requirements.txt
```

### TensorFlow installation errors

- Check your Python version.
- Use a compatible 64-bit Python installation.
- Upgrade pip and retry.
- If the issue continues, consult the official TensorFlow installation guide.

### Video window does not appear

Run the application in a local desktop terminal rather than a headless environment. The `cv2.imshow()` function requires GUI support.

### Slow performance

Emotion detection can use significant CPU resources. Close unnecessary applications, ensure good lighting, and consider processing fewer frames.

## Limitations

- Predictions may be affected by lighting, camera quality, head position, and facial occlusion.
- Facial expressions do not reliably reveal a person's true emotions or mental state.
- This project is intended for learning and demonstration, not for high-stakes decisions.

## Privacy

This code does not intentionally save or upload captured frames. Frames are processed by the installed libraries on your computer. Review any modifications and dependency behavior before use.

## Future Improvements

- Add a graphical user interface.
- Display all emotion scores.
- Add pause and resume controls.
- Support selecting a different camera.
- Improve performance by processing fewer frames.
- Add optional video recording with explicit user consent.

