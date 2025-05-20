Project Summary: Real-Time Object Detection Dashboard with YOLOv8
This project is a web-based dashboard that performs real-time object detection using YOLOv8, a state-of-the-art deep learning model. It captures video from a webcam, detects objects in each frame, and displays the results in an interactive Flask-powered web interface.

Key Features:
✔ Live Object Detection – Identifies and tracks objects in real-time with bounding boxes and confidence scores.
✔ Interactive Dashboard – Displays detection statistics (FPS, object counts, class distribution) in a modern UI.
✔ Automatic Model Download – Downloads the YOLOv8 model if missing and handles errors gracefully.
✔ Dynamic Port Handling – Falls back to port 8080 if 5000 is unavailable.
✔ Responsive Design – Works on desktop and mobile browsers.

How It Works:
Video Capture – Uses OpenCV to get frames from the webcam.

YOLOv8 Detection – Processes frames with Ultralytics YOLOv8 (pretrained on COCO dataset).

Web Dashboard – Flask serves a real-time video feed and updates stats via JavaScript.

Performance Metrics – Tracks FPS, detected objects, and class counts.

Use Cases:
Surveillance & Security – Monitor live feeds for detected objects.

Smart Retail – Track products or customer movements.

Educational Demo – Learn about real-time AI object detection.

Tech Stack:
Backend: Python (Flask, OpenCV, YOLOv8)

Frontend: HTML, CSS, JavaScript

Deployment: Local server (can be extended to cloud)