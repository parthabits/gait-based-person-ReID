# Person Re-identification using Gait Silhouettes
This repository implements a method for re-identifying persons based on their gait (walking pattern) using Gait Energy Images (GEIs) and YOLOv8 for person detection. By leveraging silhouette extraction and averaging techniques, the system is capable of re-identifying individuals across different frames in a video sequence.

## Overview
This project focuses on person re-identification through Gait Energy Images (GEI), a technique that averages a sequence of silhouette images to represent a person's unique walking pattern. The pipeline combines YOLOv8 for person detection, MediaPipe Selfie Segmentation for silhouette extraction, and re-identification based on Mean Squared Error (MSE) comparison of the silhouettes.

## Key Features:
YOLOv8 Integration: Detects individuals in video frames and crops bounding boxes.
Silhouette Extraction: Uses MediaPipe to extract a person's silhouette from the background.
Gait Energy Image (GEI) Calculation: Averages multiple frames of a person's silhouette to create a GEI representing their walking pattern.
Person Re-identification: Matches a new silhouette frame with stored GEIs to re-identify individuals.

## Installation
To install the required dependencies, we would have to simply run the following commands:

pip install ultralytics opencv-python-headless numpy scikit-image mediapipe

## Workflow
1. Frame Extraction
Extract video frames for processing between specific start and end frames.

2. Person Detection
Utilize YOLOv8 to detect individuals within the video frames and generate bounding boxes around them.

3. Silhouette Generation
Extract silhouettes from the detected persons using MediaPipe’s segmentation model, which isolates the person from the background.

4. Gait Energy Image (GEI)
Compute the GEI by averaging multiple silhouette frames for each detected person, creating a unique representation of their walking pattern.

5. Re-identification
Compare new person frames with pre-computed GEIs using Mean Squared Error (MSE). The silhouette with the lowest MSE score is matched to the corresponding individual, thus re-identifying them.

## Technique: Re-identification via Averaged Silhouette
Detection: Identify persons in video frames using YOLOv8.
Silhouette Extraction: Generate the silhouette of the detected individual using MediaPipe’s segmentation model.
Averaging: Compute the Gait Energy Image (GEI) by averaging the silhouette over a sequence of frames.
Re-identification: Re-identify individuals by comparing new silhouettes to the stored GEIs based on MSE. The best match indicates the same individual.

## Applications
Security & Surveillance: Track individuals across video footage based on their walking pattern.
Biometric Identification: Use walking pattern as a biometric trait for identifying individuals.
Behavioral Analysis: Analyze gait patterns in sports, healthcare, and motion studies.

## Conclusion
This repository showcases an efficient approach for person re-identification using gait patterns. By utilizing Gait Energy Images and silhouette extraction, the system can reliably match individuals across frames, providing a robust solution for biometric and security-based identification.
