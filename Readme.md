# Real-Time Sign Language Recognition (SLR)

[![License](https://img.shields.io/badge/license-MIT-green)](#license)

## Project Overview

This project implements a real-time sign language recognition (SLR) system that
combines visual object detection with pose-based temporal modeling.
The system integrates YOLO-based visual detection with MediaPipe pose keypoints
and LSTM-based sequence modeling to recognize sign gestures from video input.

---

## Table of Contents

- [Project Overview](#project-overview)
- [System Overview](#system-overview)
- [Key Components](#key-components)
- [Evaluation](#evaluation)
- [Demo](#demo)
- [Learning Outcomes](#learning-outcomes)
- [Limitations](#limitations)
- [License](#license)

---

## System Overview

The SLR pipeline consists of the following stages:

1. **Visual Detection**
   - YOLO is used to detect relevant regions and visual cues from each video frame.
   - Custom object annotations were prepared using Roboflow for dataset management
     and labeling.
   - Detection confidence scores are retained for downstream fusion.

2. **Pose-Based Feature Extraction**
   - MediaPipe is used to extract body and hand pose keypoints.
   - Keypoints are normalized and structured into temporal sequences.

3. **Temporal Modeling**
   - An LSTM-based sequence model processes pose keypoint sequences to predict
     sign-level probabilities over time.

4. **Hybrid Probability Fusion**
   - Final predictions are obtained by combining YOLO-based detection confidence
     and LSTM sequence predictions using weighted probability fusion.
   - This fusion improves robustness under noisy and unconstrained conditions.

---

## Key Components

- Visual Detection: YOLO
- Pose Estimation: MediaPipe
- Temporal Modeling: LSTM
- Fusion Strategy: Weighted probability-based inference
- Input: RGB video or live camera stream
- Output: Predicted sign labels in real time

---

## Evaluation

The system is evaluated using:
- **Word Error Rate (WER)** for sequence-level performance
- Task-specific accuracy metrics under real-world operating conditions

---

## Demo

A demo video illustrating real-time sign language recognition is provided:

▶️ [Full demo video]((slr_01.gif))  

---

## Learning Outcomes

Through this project, I gained experience in:

- Designing an end-to-end real-time sign language recognition pipeline
- Integrating visual detection with pose-based temporal modeling
- Applying sequence models to spatiotemporal gesture data
- Implementing probability fusion strategies for robust inference
- Evaluating SLR systems using sequence-level error metrics

---

## Limitations

- Performance may degrade under severe occlusion or rapid motion.
- LSTM-based temporal modeling may struggle with long-range dependencies.
- The system relies on accurate pose estimation from MediaPipe.

---

## Notes

- This repository focuses on **inference and system integration**.
- Training scripts and internal optimization code are not included.
- The system is designed for real-time operation in unconstrained environments.

---

## License

This project is licensed under the MIT License. See the [LICENSE](https://github.com/MinhazAyon/slr-project/blob/main/LICENSE) file for details.

---

## Contact

- **Author:** Minhaz Uddin  
- **Email:** minhaz182219@gmail.com  
- **GitHub:** [github.com/MinhazAyon](https://github.com/MinhazAyon)
- **Whatsapp:** 01628182219
