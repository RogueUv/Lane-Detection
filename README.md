# Lane Detection System

A computer vision-based **Lane Detection System** developed using **Python and OpenCV** to identify road lane markings from images and video frames.

The system processes road scenes using image-processing techniques such as **Canny Edge Detection, Region of Interest (ROI) masking, and Hough Line Transform** to detect and visualize lane boundaries.

## 📌 Features

* Detects lane markings from road images/video frames
* Converts frames to grayscale for efficient processing
* Applies Gaussian Blur to reduce image noise
* Uses Canny Edge Detection to identify road edges
* Defines a Region of Interest (ROI) to focus on the driving area
* Uses Hough Line Transform to detect lane-line segments
* Draws detected lane lines over the original road frame
* Supports real-time/video-based lane detection
* Provides a foundation for advanced ADAS and autonomous-driving applications

## 🛠️ Technologies Used

* **Python**
* **OpenCV**
* **NumPy**
* **Computer Vision**
* **Image Processing**
* **Hough Line Transform**
* **Canny Edge Detection**

## 🔄 How It Works

The system follows a sequence of image-processing steps:

```text
Input Image / Video
        ↓
Grayscale Conversion
        ↓
Gaussian Blur
        ↓
Canny Edge Detection
        ↓
Region of Interest Masking
        ↓
Hough Line Transform
        ↓
Lane Line Detection
        ↓
Overlay Detected Lanes
        ↓
Output Frame
```

## 🧠 Detection Pipeline

### 1. Grayscale Conversion

The input frame is converted from RGB/BGR to grayscale to simplify image processing and reduce computational complexity.

### 2. Gaussian Blur

Gaussian filtering is applied to reduce noise and smooth the image before edge detection.

### 3. Canny Edge Detection

The Canny algorithm identifies strong edges in the road image, which helps isolate lane markings.

### 4. Region of Interest

A polygonal ROI is applied to focus processing on the portion of the road where lane markings are expected.

Example ROI points:

```python
[(200, h), (1100, h), (550, 250)]
```

where `h` represents the height of the frame.

### 5. Hough Line Transform

The Hough Line Transform detects line segments from the extracted edges and identifies potential lane boundaries.

### 6. Lane Visualization

The detected lane lines are drawn onto the original frame to provide a visual representation of the detected road lanes.

## 📂 Project Structure

```text
Lane-Detection/
│
├── main.py
├── model.h5
├── requirements.txt
├── README.md
│
├── input/
│   └── road_video.mp4
│
└── output/
    └── detected_lanes.mp4
```

> Update the filenames and folder structure according to the actual contents of your repository.

## ⚙️ Installation

Clone the repository:

```bash
git clone https://github.com/RogueUv/Lane-Detection.git
```

Navigate to the project directory:

```bash
cd Lane-Detection
```

Install the required dependencies:

```bash
pip install -r requirements.txt
```

If `requirements.txt` is not available, install the main dependencies manually:

```bash
pip install opencv-python numpy
```

## ▶️ Running the Project

Run the main Python script:

```bash
python main.py
```

The system will process the input image/video and generate frames with the detected lane boundaries.

## 📊 Example Processing

The system identifies lane boundaries through the following process:

```text
Road Frame
   ↓
Edge Detection
   ↓
ROI Extraction
   ↓
Line Segment Detection
   ↓
Left/Right Lane Identification
   ↓
Lane Overlay
```

## 🚘 Applications

This project demonstrates concepts that can be applied to:

* Advanced Driver Assistance Systems (ADAS)
* Lane Departure Warning Systems
* Autonomous Driving
* Road-Safety Applications
* Intelligent Transportation Systems
* Real-time Computer Vision

## 🔮 Future Improvements

Potential improvements include:

* Real-time lane tracking
* Curved lane detection
* Lane departure warning
* Perspective transformation / Bird's-Eye View
* Deep-learning-based lane detection
* Improved performance under low-light and adverse weather conditions
* Integration with ADAS systems
* Distance and vehicle-position estimation
* Deployment on edge devices

## ⚠️ Limitations

The current approach primarily relies on traditional computer-vision techniques and may be affected by:

* Poor lighting conditions
* Rain, fog, or snow
* Faded lane markings
* Sharp curves
* Occluded lane markings
* Complex road environments
