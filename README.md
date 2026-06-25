# Human Pose & Gesture Recognition – Safety System with Real-Time Alert System
### Real-Time Tracking with MediaPipe Holistic, LSTM & Location-Based Alerts

[![Python version](https://img.shields.io/badge/python-3.x-blue)]()
[![TensorFlow](https://img.shields.io/badge/TensorFlow-2.x-orange)]()
[![MediaPipe](https://img.shields.io/badge/MediaPipe-Holistic-teal)]()
[![License](https://img.shields.io/badge/license-MIT-green)]()

---

### Project Overview  
This project implements a real-time human pose and gesture recognition system designed for safety and emergency alerting, especially for women's safety.  
It uses MediaPipe Holistic for body, face, and hand landmark detection, and a TensorFlow LSTM model for gesture classification.  
When a distress or help gesture is detected, the system automatically sends an SMS alert containing the user's live location (via Geocoder) using Twilio API.

Watch the demo video on YouTube: https://youtu.be/cWUQyDXmYO8?si=JcIuF2p5LZFx-JMq

---

### Features
- Real-time gesture recognition using OpenCV and MediaPipe  
- Deep learning-based gesture classification (LSTM model)  
- Automated safety alerts with live location tracking (Geocoder)  
- SMS notifications via Twilio API  
- Modular structure for collection → preprocessing → model training → real-time detection  
- Visual feedback overlays of keypoints and gestures  

---

### Technologies Used  
| Category | Tools / Libraries |
|-----------|------------------|
| Programming Language | Python |
| Computer Vision | OpenCV |
| Landmark Detection | MediaPipe (Holistic) |
| Deep Learning | TensorFlow / Keras |
| Location Tracking | Geocoder |
| Communication | Twilio API |
| Data Handling | NumPy, Pandas |
| Visualization | Matplotlib |

---

### Project Structure  
```
/project-root
│  
├── trishul.ipynb             # Jupyter notebook with model training & real-time testing  
├── /data                     # Collected keypoint datasets  
├── /models                   # Trained LSTM model weights  
├── /scripts  
│   ├── collect_data.py  
│   ├── train_model.py  
│   ├── real_time_predict.py  
│   └── send_alert.py         # Contains Twilio + Geocoder alert logic  
└── README.md                 # This file  
```

---

### How to Run  
#### Step 1: Install Dependencies  
```bash
pip install opencv-python mediapipe tensorflow matplotlib numpy pandas scikit-learn geocoder twilio
```

#### Step 2: Run the Notebook  
Execute all sections in trishul.ipynb sequentially:
1. Data Collection via webcam  
2. Keypoint Extraction & Preprocessing  
3. LSTM Model Training & Evaluation  
4. Real-Time Prediction & Visualization  
5. (Optional) Trigger SMS Alerts with Live Location

---

### Alert System with Geocoder + Twilio  

When a "HELP" gesture is detected, the system automatically:
1. Uses Geocoder to get the latitude, longitude, and address  
2. Formats an alert message with these details  
3. Sends it to the registered contact using Twilio SMS API



How It Works:
- The model identifies gestures in real-time from webcam input.  
- When "HELP" or similar is recognized, it triggers send_safety_alert().  
- Geocoder fetches the user's approximate current location using IP.  
- Twilio sends the SMS to the registered emergency contact instantly.  

---

### Model Performance  
- High gesture recognition accuracy (evaluated via confusion matrix & accuracy)  
- Robust in various lighting conditions  
- Real-time inference with low latency using MediaPipe & TensorFlow  

---

### Demo Preview  
Watch the demo video: https://youtu.be/cWUQyDXmYO8?si=JcIuF2p5LZFx-JMq  
Shows real-time gesture detection, pose visualization, and SMS alert functionality.  

(You can add a GIF or screenshot from your demo here.)

---

### Future Enhancements  
- Integrate GPS for precise mobile-based tracking  
- Add voice or sound-triggered alerts for emergencies  
- Support multi-person detection and classification  
- Deploy as a python
- Extend to IoT devices / wearable sensors  



