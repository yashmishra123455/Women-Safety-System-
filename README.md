# Women Safety System

### AI-Based Emergency Gesture Detection and Live Safety Notification Framework

[![Python](https://img.shields.io/badge/Python-3.x-blue)]()
[![TensorFlow](https://img.shields.io/badge/TensorFlow-2.x-orange)]()
[![MediaPipe](https://img.shields.io/badge/MediaPipe-Holistic-green)]()
[![Status](https://img.shields.io/badge/Status-Active-success)]()

---

## Overview

**Sentinel Gesture** is an intelligent safety monitoring system that performs **real-time body pose and hand gesture analysis** to identify emergency or distress signals from a live camera feed. The system is designed as a rapid-response safety solution, where suspicious or predefined emergency gestures can activate an automated alert workflow.

The project combines **MediaPipe Holistic** for extracting facial, pose, and hand landmarks with a **TensorFlow LSTM-based sequence model** for temporal gesture classification. Once a critical gesture is recognized, the system triggers an alert mechanism that retrieves the user’s approximate location and forwards it to a saved emergency contact using SMS.

This solution is particularly useful for **personal safety applications**, smart surveillance prototypes, and AI-assisted emergency response systems.

**Demo Video:** https://youtu.be/cWUQyDXmYO8?si=JcIuF2p5LZFx-JMq

---

## Core Functionalities

* **Live Gesture Monitoring** through webcam-based video capture
* **Pose + Hand Landmark Extraction** using MediaPipe Holistic
* **Sequence-Based Gesture Recognition** using an LSTM deep learning model
* **Emergency Alert Triggering** when a danger/help gesture is detected
* **Location-Aware SMS Notification** using Geocoder and Twilio
* **Visual Display Layer** for showing detected landmarks and predicted actions
* **Structured ML Workflow** covering data collection, preprocessing, training, and deployment testing

---

## Tech Stack

| Domain                     | Tools / Frameworks |
| -------------------------- | ------------------ |
| Language                   | Python             |
| Video Processing           | OpenCV             |
| Landmark Detection         | MediaPipe Holistic |
| Deep Learning              | TensorFlow / Keras |
| Alert Messaging            | Twilio API         |
| Location Retrieval         | Geocoder           |
| Numerical Processing       | NumPy, Pandas      |
| Evaluation / Visualization | Matplotlib         |

---

## System Pipeline

The project follows a sequential AI pipeline:

1. **Capture human movement data** using webcam input
2. **Extract body, face, and hand keypoints** frame-by-frame
3. **Create temporal gesture sequences** for model learning
4. **Train an LSTM model** on action/gesture patterns
5. **Run real-time inference** on incoming video frames
6. **Trigger emergency communication** when a distress gesture is classified

---

## Project Directory

```bash
/Sentinel-GestureGuard
│
├── gesture_safety_notebook.ipynb      # Main notebook for training + live testing
├── /gesture_dataset                   # Stored keypoint sequence data
├── /trained_models                    # Saved model files / weights
├── /core_modules
│   ├── dataset_builder.py             # Gesture sample collection
│   ├── sequence_trainer.py            # LSTM training and evaluation
│   ├── live_monitor.py                # Real-time gesture prediction
│   └── emergency_notifier.py          # SMS + location alert logic
└── README.md
```

---

## Installation

Install the required dependencies before running the project:

```bash
pip install opencv-python mediapipe tensorflow matplotlib numpy pandas scikit-learn geocoder twilio
```

---

## Execution Guide

### 1. Launch the Notebook

Run the notebook file step-by-step:

```bash
gesture_safety_notebook.ipynb
```

### 2. Workflow Execution

The notebook generally follows these stages:

* **Stage 1:** Gesture data acquisition from webcam
* **Stage 2:** Keypoint extraction and preprocessing
* **Stage 3:** LSTM model creation and training
* **Stage 4:** Performance testing and real-time prediction
* **Stage 5:** Emergency alert activation on target gesture detection

---

## Emergency Alert Module

The alert subsystem is activated whenever the model predicts a predefined emergency gesture such as **HELP** or any configured distress signal.

### Alert Workflow

1. Detect the emergency gesture from the live video stream
2. Fetch approximate geographic details using **Geocoder**
3. Prepare an alert message containing location coordinates/address
4. Send the notification to a registered contact using **Twilio SMS API**

### Alert Message Includes

* Emergency trigger status
* Latitude and longitude
* Approximate detected address/location
* Safety warning message for the receiver

---

## Working Principle

The overall working logic of the system is:

* A webcam continuously captures the user’s movements.
* MediaPipe Holistic extracts pose, hand, and facial landmarks from each frame.
* These keypoints are arranged into sequential data samples.
* The trained LSTM model classifies whether the sequence matches a learned gesture pattern.
* If the detected action corresponds to an emergency signal, the alert function is called automatically.
* The system then retrieves location details and sends an SMS notification to the emergency contact.

---

## Performance Highlights

* Supports **real-time gesture inference**
* Efficient landmark extraction with **low-latency processing**
* Temporal sequence learning improves action recognition quality
* Can be adapted for **personal safety**, **smart monitoring**, or **gesture-controlled alert systems**

---

## Demo

**YouTube Demonstration:**
https://youtu.be/cWUQyDXmYO8?si=JcIuF2p5LZFx-JMq

The demo includes:

* Live pose and gesture recognition
* Landmark visualization
* Distress gesture prediction
* SMS-based emergency notification workflow

---

## Possible Enhancements

* Integrate **GPS-based location sharing** for more precise tracking
* Add **voice-triggered emergency activation**
* Extend support for **multiple users/person detection**
* Convert the prototype into a **desktop or mobile application**
* Connect with **IoT wearables** or safety devices for hybrid monitoring
* Add a **cloud dashboard** for alert history and event logs

---

## Application Areas

* Women’s personal safety systems
* Smart surveillance and security prototypes
* AI-based emergency response systems
* Gesture-enabled alert solutions
* Human activity monitoring applications

---

## Conclusion

Sentinel GestureGuard demonstrates how **computer vision**, **sequence modeling**, and **real-time alerting** can be combined into a practical emergency-response prototype. By using gesture recognition as an input trigger and automating communication with location sharing, the project presents a scalable foundation for safety-oriented intelligent systems.
