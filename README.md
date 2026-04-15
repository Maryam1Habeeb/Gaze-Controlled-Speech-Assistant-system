# Gaze-Controlled-Speech-Assistant-system
A gaze-based communication system that uses webcam eye tracking and machine learning to help users select words and phrases through gaze interaction. The system includes gaze calibration, real-time prediction, button selection, and text-to-speech output.

The system combines real-time webcam tracking, facial landmark extraction, personal gaze calibration, gaze-to-button selection, and text-to-speech output. It is designed to support communication through eye movement, especially for users who have difficulty using a keyboard, mouse, or touch screen.

## Project Idea

The main goal of this project is to build an assistive communication interface controlled by the user's gaze.  
The user looks at buttons displayed on the screen, and the system estimates the gaze position using a webcam. When the gaze remains on a button, the button is selected, and the related word or phrase is added or spoken.

## Features

- Real-time webcam-based gaze tracking
- Face and eye landmark detection
- Personal calibration for improved accuracy
- Gaze-based button selection
- Main category and suggestion buttons
- Phrase and sentence building
- Text-to-speech output using Piper TTS
- Simple web interface
- Modular JavaScript structure
- Calibration data collection and cleaning
- Mapping comparison for improving gaze accuracy

## Technologies Used

- Python
- Flask
- Flask-SocketIO
- OpenCV
- MediaPipe
- PyTorch
- NumPy
- Pandas
- Scikit-learn
- HTML
- CSS
- JavaScript
- Piper Text-to-Speech

## Project Structure

```text
final3/
│
├── app/
│   ├── app.py
│   ├── templates/
│   │   └── index.html
│   ├── static/
│   │   ├── css/
│   │   │   ├── style.css
│   │   │   └── background.css
│   │   └── js/
│   │       ├── socket.io.min.js
│   │       ├── data.js
│   │       ├── state.js
│   │       ├── helpers.js
│   │       ├── popups.js
│   │       ├── audio.js
│   │       ├── ui.js
│   │       ├── gaze.js
│   │       ├── welcome.js
│   │       ├── app.js
│   │       └── export_button_coordinates.js
│   └── piper/
│       ├── piper.exe
│       ├── en_US-hfc_female-medium.onnx
│       └── en_US-hfc_female-medium.onnx.json
│
├── calibration/
│   ├── collect_data.py
│   ├── filter_bad_images.py
│   ├── feature_extraction.py
│   ├── train_calibrator.py
│   ├── compare_mappings.py
│   ├── fit_mapping.py
│   ├── data/
│   └── models/
│
└── run_app.bat
```

## Main Components
# 1. Web Application
The web application is located inside the app/ folder.
It includes:
app.py: Runs the Flask server and connects the backend with the interface.
templates/index.html: Main user interface page.
static/css/: Styling files for the interface.
static/js/: JavaScript files for UI behavior, gaze interaction, audio, and button selection.
piper/: Text-to-speech files used to generate spoken output.
# 2. Calibration System
The calibration process is located inside the calibration/ folder.
It includes scripts for:
Collecting calibration images
Filtering bad or unclear images
Extracting facial landmarks
Training a personal calibrator model
Comparing different gaze mapping methods
Saving the best gaze mapping model
# 3. Text-to-Speech
The system uses Piper TTS to convert selected words or phrases into speech.
This allows the system to generate audio output locally.

## How It Works
The user opens the web application.
The webcam captures the user's face.
MediaPipe detects face and eye landmarks.
The trained calibration model predicts the gaze position.
The predicted gaze point is mapped to the screen.
The system checks which button the user is looking at.
After selection, the word or phrase is added to the sentence.
The selected phrase can be spoken using text-to-speech.
## Calibration Workflow
The calibration workflow helps improve gaze accuracy for the user.
```text
python collect_data.py
python filter_bad_images.py
python feature_extraction.py
python train_calibrator.py
python fit_mapping.py
python compare_mappings.py
```
The output files are saved in:
```text
calibration/data/processed/
calibration/data/mappings/
calibration/models/
```


