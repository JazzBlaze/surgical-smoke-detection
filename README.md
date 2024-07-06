# Real-Time Smoke Detection Using Hybrid Image Processing Model

## Overview

This project aims to develop a real-time smoke detection system using a hybrid image processing model that combines HSV thresholding and a custom Pixel CNN. This approach is designed to enhance the accuracy and efficiency of detecting smoke in various scenarios, including 3D data such as medical scans and videos.

## Methods

### Method 1: HSV_Threshold Image Processing
- **Description**: A no-machine learning model suitable for real-time detection.
- **Performance**: Surpassed expectations in detecting no-smoke images during testing.

### Method 2: Custom based Pixel CNN Model
- **Description**: Useful for processing 3D data like medical scans and videos due to its ability to analyze spatial relationships in all directions.

### Method 3: Hybrid Model (Final Model)
- **Description**: Combines HSV thresholding and Pixel CNN for better accuracy.
- **Advantages**: As HSV is a no-CNN approach, training and testing time is avoided, making it advantageous for real-time detection.

## Pre-Processing
- **Tools**: Utilized OpenCV and Pillow libraries.
- **Techniques**: Thresholding, contour analysis, and Hough Transform for circle detection.
- **Frame Size**: Resized frames to 244x244 for optimal processing.
- **Noise Reduction**: Applied Gaussian Blur to remove noise.

## Training, Validation & Testing
- **Dataset**: 60 videos.
  - Training: 80% (48 videos)
  - Validation: 10% (6 videos)
  - Testing: 10% (6 videos)
- **Parameters**: 
  - Number of epochs: 10
  - Batch size: 16
  - Training time: 2 hours for input size 244x244, 48 videos, 10 epochs, batch size 16.
- **Hardware**: 
  - Platform: Kaggle private virtual machines.
  - GPU: T4 x2
  - Tools: TensorFlow 2.15.1, Keras, OpenCV

## Architecture
![image](https://github.com/JazzBlaze/surgical-smoke-detection/assets/141245778/004dd4dd-a651-4fbb-9f73-75ebbaea0130)


## Metrics
- **HSV-Threshold**:
  - Accuracy: 89.10%
  - F1-Score: 50.22
  - Recall: 33.98
  - Precision: 59.56
- **Custom Pixel CNN**:
  - Accuracy: 86.83%
  - F1-Score: 55.97
  - Recall: 62.12
  - Precision: 50.93
- **Hybrid**:
  - Accuracy: 83.13%
  - F1-Score: 82.9
  - Recall: 83.16
  - Precision: 82.7

## Inference Speed
- **HSV-Threshold**: 99 seconds
- **Custom Pixel CNN**: 1066 seconds
- **Hybrid**: 816 seconds

## Inference Results
![image](https://github.com/JazzBlaze/surgical-smoke-detection/assets/141245778/c5a6b772-ed45-4510-8a07-447d6fe99f3d)
![image](https://github.com/JazzBlaze/surgical-smoke-detection/assets/141245778/05c10a97-47d0-4d5b-ad62-76aabde64086)

## Real-Time Smoke Detection
- **Process**: 
  - Videos are processed 10 frames at a time to consider the temporal correlation of sequences.
  - Predictions are made using the hybrid model for smoke or no smoke.
  - Frames are labeled and stitched back together for real-time output.

## Conclusion
- The hybrid model provides a robust and efficient solution for real-time smoke detection, leveraging the strengths of both HSV thresholding and custom Pixel CNN technique.
