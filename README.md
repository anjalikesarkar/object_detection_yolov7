# object_detection_yolov7
 “YOLOv7 experiments – image, webcam, and multi-webcam object detection with Jupyter notebooks.”

# YOLOv7 - Object Detection Experiments
This repository contains a set of hands-on experiments using [YOLOv7](https://github.com/WongKinYiu/yolov7) 
for real-time object detection tasks, implemented in Jupyter notebooks.

# Project Overview
 - These experiments cover:
  1. **Image Detection** – Run YOLOv7 on static images.
  2. **Webcam Detection** – Perform real-time object detection using a webcam.
  3. **Multi-Webcam Detection** – Detect objects on multiple webcams in parallel.

# Requirements
 - torch>=1.7
 - opencv-python
 - matplotlib
 - notebook
 - numpy

# Image Detection
- This notebook demonstrates how to perform object detection on static images with YOLOv7. The key steps include:
 1. Load the YOLOv7 model using `torch.hub.load()` with the custom weights.
 2. Read the input image with OpenCV (`cv2.imread`).
 3. Convert the image from BGR to RGB format for model compatibility.
 4. Run the YOLOv7 model inference on the RGB image.
 5. Render bounding boxes on the image.
 6. Convert the image back from RGB to BGR if needed for saving or display.
 7. Visualize the detection results using Matplotlib.
 8. 
# Webcam Live Object Detection
 - This notebook demonstrates real-time object detection using a webcam with YOLOv7. The main steps are:
  1. Load the YOLOv7 model with `torch.hub.load()`.
  2. Create a folder to save detection results.
  3. Capture video frames from the webcam using `cv2.VideoCapture(0)`.
  4. Convert each frame from BGR to RGB.
  5. Pass the RGB frame through the YOLOv7 model for inference.
  6. Render detection bounding boxes on the frame.
  7. Convert the frame back from RGB to BGR.
  8. Save and display the processed frames in real-time.
  9. If we have to save it as a video need to declare fourcc and videowriter

# Multi-Webcam Object Detection
 - This notebook demonstrates object detection across multiple webcam streams simultaneously using YOLOv7. The key steps include:
  1. Define a function to arrange multiple frames into a grid using rows, columns, and NumPy stacking (`hstack` and `vstack`).
  2. Load the YOLOv7 model using `torch.hub.load()`.
  3. Initialize video capture objects (`caps`) for each webcam and loop through them to read frames.
  4. Convert each frame from BGR to RGB.
  5. Pass each RGB frame through the YOLOv7 model for detection.
  6. Render bounding boxes on each frame.
  7. Convert frames back from RGB to BGR.
  8. Append processed frames to a list or array.
  9. Combine all frames into a single grid display using the grid function.
  10. Create a directory to save output and save the combined results as images or video files.
