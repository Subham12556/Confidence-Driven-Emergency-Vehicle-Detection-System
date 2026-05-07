# 🚨 Confidence-Driven Emergency Vehicle Detection System

> A Multimodal Deep Learning Framework for Real-Time Emergency Vehicle Priority Detection in Urban Traffic Environments

---

# 📖 Overview

This project presents a **multimodal AI-based emergency vehicle detection system** that combines **computer vision** and **audio signal processing** for robust and reliable emergency vehicle identification in complex urban traffic environments.

The system integrates:

- **Custom YOLOv12-based object detection**
- **Deep CNN-based siren classification**
- **Decision-level confidence fusion**
- **Real-time dual-stream inference**
- **Priority classification mechanism**

Traditional single-modality systems often fail under challenging conditions such as:
- Occlusion
- Dense traffic
- Low visibility
- Environmental noise
- Motion blur

To overcome these limitations, this project combines both:
- **Vision modality** → detects emergency vehicles visually
- **Audio modality** → detects siren sounds acoustically

The final system uses a **confidence-driven fusion mechanism** to generate reliable real-time emergency vehicle priority decisions.

---

# 🎯 Objectives

The primary objectives of this project are:

- Detect emergency vehicles in real-time urban environments
- Improve small-object detection in dense traffic
- Build a robust siren classification system
- Reduce false positives and missed detections
- Combine visual and audio intelligence using multimodal fusion
- Achieve strong cross-dataset generalization
- Develop a scalable and deployment-ready AI system

---

# 🧠 Key Features

## 🚗 Vision-Based Emergency Vehicle Detection
- Custom YOLOv12 architecture
- P2–P5 multi-scale detection
- Small-object optimization
- Real-time bounding box detection
- High recall-focused training

## 🔊 Audio-Based Siren Classification
- Deep CNN-based audio classification
- Mel Spectrogram feature extraction
- Noise-robust augmentation
- Multi-model comparison and ensemble learning

## 🔀 Multimodal Fusion
- Decision-level confidence fusion
- Weighted scoring mechanism
- Dynamic priority classification
- High / Medium / Low priority outputs

## ⚡ Real-Time Processing
- Parallel audio-video inference
- Asynchronous pipeline execution
- Optimized low-latency architecture

## 🌍 Cross-Dataset Generalization
- UrbanSound8K evaluation
- ESC-50 evaluation
- Multi-domain training setup

---

# 🏗 System Architecture

The proposed architecture consists of two independent processing pipelines:

## 1️⃣ Vision Pipeline
The vision module processes real-time video streams using a custom YOLOv12 detector.

### Workflow
- Frame capture
- Image preprocessing
- YOLO inference
- Bounding box generation
- Confidence extraction

### Key Improvements
- P2 detection layer integration
- Enhanced feature fusion
- Optimized augmentation strategy
- Improved recall for small objects

---

## 2️⃣ Audio Pipeline
The audio module processes siren sounds using deep learning-based classification.

### Workflow
- Audio capture
- STFT transformation
- Mel spectrogram generation
- CNN classification
- Confidence extraction

### Audio Models Implemented
- DenseNet
- MobileNet
- EfficientNetV2
- ResNet50V2

---

## 3️⃣ Fusion Module

The outputs of both modalities are combined using:

F = α·Cv + (1−α)·Ca

Where:
- `Cv` = Visual confidence
- `Ca` = Audio confidence
- `α` = Vision weight

The system assigns:
- High Priority
- Medium Priority
- Low Priority

based on the final fusion score.

---

# 📂 Dataset Information

## 📸 Image Dataset
Custom emergency vehicle dataset containing:
- Ambulance
- Fire Truck
- Police Vehicle
- Non-Emergency Vehicles
DATASET_LINK:-
https://www.kaggle.com/datasets/subham12098/balanced-dataset/data

### Dataset Processing
- Duplicate removal
- Invalid annotation correction
- Dataset balancing
- Noise reduction
- Data augmentation

### Final Dataset Size
- 37K+ processed images

---

## 🔉 Audio Dataset

### Primary Dataset
- sireNNet
DATASET_LINK:-
https://data.mendeley.com/datasets/j4ydzzv4kb/1

### Cross-Dataset Evaluation
- UrbanSound8K
DATASET_LINK:-
https://urbansounddataset.weebly.com/urbansound8k.html
- ESC-50
DATASET_LINK:-
https://github.com/karolpiczak/ESC-50

### Audio Augmentation Techniques
- Time shifting
- Pitch shifting
- Time stretching
- Noise injection
- SpecAugment
- MixUp

---

# 🔬 Vision Model Comparison

| Model | Precision | Recall | mAP@50 |
|---|---|---|---|
| YOLOv8 | 0.893 | 0.705 | 0.780 |
| YOLOv11 | 0.859 | 0.728 | 0.787 |
| YOLOv12 | 0.874 | 0.731 | 0.804 |

YOLOv12 achieved the best balance between:
- Precision
- Recall
- Overall detection quality

Therefore, YOLOv12 was selected and further modified.

---

# 🚀 Modified YOLOv12 Performance

| Metric | Score |
|---|---|
| mAP@50 | 0.8855 |
| mAP@50–95 | 0.5854 |
| Recall | 0.8284 |
| Precision | 0.9128 |

---

# 🔊 Audio Model Performance

| Model | Accuracy | F1-Score | Parameters |
|---|---|---|---|
| DenseNet | 0.9821 | 0.9822 | 651K |
| MobileNet | 0.9762 | 0.9761 | 239K |
| EfficientNetV2 | 0.9405 | 0.9405 | 6.2M |
| ResNet50V2 | 0.9940 | 0.9942 | 24.1M |

---

# 🌍 Cross-Dataset Evaluation

| Dataset | Setup A | Setup B |
|---|---|---|
| UrbanSound8K | 0.8309 | 0.9427 |
| ESC-50 | 0.5300 | 0.7500 |

### Setup A
Zero-shot testing without external dataset training.

### Setup B
Multi-domain training with diverse environmental noise exposure.

---

# 📊 SNR Robustness Analysis

The models were evaluated under varying Signal-to-Noise Ratios (SNR):

- -5 dB
- 0 dB
- 5 dB
- 10 dB
- 15 dB
- 20 dB

Results demonstrated strong robustness under noisy urban conditions.

---

# ⚙️ Technologies Used

## Programming Languages
- Python 3.9+

## Frameworks & Libraries
- PyTorch
- TensorFlow
- Keras
- OpenCV
- Librosa
- NumPy
- Pandas
- Matplotlib

## Deep Learning
- YOLOv12
- CNN
- DenseNet
- MobileNet
- EfficientNetV2
- ResNet50V2

---
Deployment

The system supports:

Real-time webcam inference
Live microphone input
GPU acceleration
Parallel processing
Edge deployment optimization

Future Work

Future improvements may include:

Transformer-based multimodal fusion
Edge AI deployment
Smart traffic signal integration
IoT-based emergency response systems
Vehicle-to-Infrastructure (V2I) communication
Real-time cloud deployment
Advanced domain adaptation

License

This project is licensed under the MIT License.

Author
Subham Kundu
Final Year Major Project – 2026

# Research Publication

A research paper based on this project has been submitted to the:

🏛️ 8th International Conference on Computational Intelligence in Communications and Business Analytics (CICBA 2026)

Paper Title:
“A Confidence Driven Multi Model System for Emergency Vehicle Priority in Urban Traffic using Deep Learning”
