# Smart Surveillance System

This repository contains a **Smart Surveillance System** that uses **YOLO (You Only Look Once)** and **Darknet** to perform real-time detection tasks such as **Object Detection**, **Social Distancing Monitoring**, **Fall Detection**, and **Vehicle Crash Detection**. The system processes video streams from either a webcam or video URL and provides real-time results via a web interface built with **Flask**.

## Features
- **Object Detection**: Detect various objects like people, cars, bicycles, etc., and label them with colored bounding boxes.
- **Social Distancing Detection**: Monitor the distance between people and alert when the threshold distance is violated.
- **Fall Detection**: Detect human falls based on object movement patterns.
- **Vehicle Crash Detection**: Detect vehicle crashes based on proximity and intersection of vehicle bounding boxes.

## Technologies
- **YOLOv4-tiny**: For real-time object detection.
- **Darknet**: The deep learning framework for YOLO.
- **Flask**: Python microframework for creating the web interface.
- **OpenCV**: Video capture and image processing.

## Requirements

1. **Python** (version 3.x)
2. **YOLOv4-tiny**: You can download the required YOLO weights and configuration files [here](https://github.com/AlexeyAB/darknet#how-to-train-to-detect-your-custom-objects).
3. **Darknet**: Follow the installation instructions for Darknet from the [Darknet GitHub repository](https://github.com/AlexeyAB/darknet).
4. **OpenCV**: For video processing, ensure OpenCV is installed:
   ```bash
   pip install opencv-python
   ```
5. **Flask**: Install Flask for the web server:
   ```bash
   pip install Flask
   ```

## Installation and Setup

1. Clone the repository:
   ```bash
   git clone https://github.com/Prathamesh326/SmartSurveillanceSystem-main.git
   cd SmartSurveillanceSystem-main
   ```

2. Install the required Python dependencies:
   ```bash
   pip install -r requirements.txt
   ```

3. Download and set up YOLO configuration and weights:
   - **YOLO Config File**: [yolov4-tiny.cfg](https://github.com/AlexeyAB/darknet/blob/master/cfg/yolov4-tiny.cfg)
   - **YOLO Weights File**: [yolov4-tiny.weights](https://github.com/AlexeyAB/darknet#pre-trained-models)
   - Place these files in the corresponding directory (update paths in the code if necessary):
     ```
     C:/Yolo_v4/darknet-darknet_yolo_v4_pre/build/darknet/x64/cfg/
     ```

4. Update `coco.data` file:
   ```
   C:/Yolo_v4/darknet-darknet_yolo_v4_pre/build/darknet/x64/cfg/coco.data
   ```

5. Launch the Flask application:
   ```bash
   python app.py
   ```

6. Open your browser and go to `http://127.0.0.1:5000/` to access the system.

## Usage

Once the application is running, the following routes are available:

1. **Home** (`/`): The homepage of the system.
2. **Object Detection** (`/ObjectDetection`): Detect and label objects in real-time.
3. **Social Distancing Detection** (`/SocialDistancingDetection`): Monitor social distancing violations.
4. **Fall Detection** (`/FallDetection`): Detect human falls.
5. **Vehicle Crash Detection** (`/VehicleCrashDetection`): Detect potential vehicle crashes.

### Uploading a Video
You can upload a video URL via the `/Video` route:
1. Navigate to `http://127.0.0.1:5000/Video`.
2. Submit the video URL and the system will process it.

### Viewing Real-Time Video Stream
The processed video stream can be viewed at `http://127.0.0.1:5000/video_feed`.

## Folder Structure

```
SmartSurveillanceSystem-main/
│
├── templates/                     # HTML templates for the web interface
│   ├── Shady.html
│   ├── FallDetection.html
│   ├── ObjectDetection.html
│   ├── SocialDistancingDetection.html
│   └── VehicleCrashDetection.html
│
├── app.py                          # Main Flask application
├── requirements.txt                # Python dependencies
├── README.md                       # This README file
└── static/                         # Static files like CSS, JS, etc.
```

## Future Improvements
- **Custom Model Training**: Extend the system with a custom-trained YOLO model for specific use cases.
- **Improved Crash Detection**: Enhance the vehicle crash detection logic with additional parameters such as speed and orientation.
- **Alert System**: Implement an alert system that sends notifications in case of detected violations or crashes.
