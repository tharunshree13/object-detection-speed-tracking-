# 🚗 Intelligent Video Surveillance — Vehicle Detection & Speed Tracking

> A computer vision system for real-time vehicle detection and speed estimation using YOLOv5/YOLOv8 and deep learning-based tracking algorithms.

---

## 📌 Project Overview

This project implements an **Intelligent Video Surveillance** system that detects vehicles and tracks their speed in real time from surveillance camera footage — without the need for physical road sensors or radar hardware.

The system uses deep learning object detection (YOLO), multi-object tracking (DeepSORT), and frame-based speed estimation to deliver automated traffic monitoring suitable for urban roads, highways, and smart city deployments.

**College:** Vinayaka Mission's Kirupananda Variyar Engineering College (VMKV), Salem  
**Department:** Computer Science and Engineering  
**Academic Year:** 2024–2025  
**Developed by:** Tharun Shree B (3592210051)  
**Supervisor:** Mr. V. Amirthalingam, M.E., Ph.D.

---

## 🎯 Features

- **Real-Time Vehicle Detection** — Detects cars, trucks, bikes, and buses in live or recorded video using YOLOv5/YOLOv8
- **Multi-Object Tracking** — Tracks each vehicle across frames with consistent ID assignment using DeepSORT / SORT
- **Speed Estimation** — Calculates vehicle speed (km/h) using pixel displacement and real-world camera calibration
- **Works Without Road Sensors** — Pure computer vision approach; no radar or inductive loop required
- **Output Video** — Annotated video with bounding boxes and speed labels rendered on each vehicle
- **Scalable** — Deployable on edge devices or cloud-connected systems for 24/7 monitoring

---

## 🧠 Tech Stack

| Component | Technology |
|---|---|
| Language | Python 3.8+ |
| Object Detection | YOLOv5 / YOLOv8 (Ultralytics) |
| Tracking Algorithm | DeepSORT / Custom ID Assignment |
| Computer Vision | OpenCV |
| Deep Learning | PyTorch / TensorFlow |
| Numerical Computing | NumPy, SciPy |
| Visualization | OpenCV, Matplotlib |
| Optional GUI | Tkinter / Flask / Streamlit |
| Database (optional) | MySQL / PostgreSQL / MongoDB |

---

## ⚙️ System Requirements

### Software
- Python 3.8 or above
- Windows 10/11 or Ubuntu 20.04+
- CUDA-enabled GPU drivers (for real-time inference)

### Hardware
- HD/4K IP Camera (for live deployment)
- NVIDIA GPU (GTX/RTX series recommended for real-time performance)
- SSD/HDD for video storage
- Stable network connection for IP camera streaming

---

## 🚀 Getting Started

### 1. Clone the Repository
```bash
git clone https://github.com/tharunshree13/intelligent-video-surveillance.git
cd intelligent-video-surveillance
```

### 2. Install Dependencies
```bash
pip install -r requirements.txt
```

### 3. Download YOLOv5 Weights
```bash
# YOLOv5 weights are auto-downloaded on first run, or manually:
wget https://github.com/ultralytics/yolov5/releases/download/v6.0/yolov5s.pt
```

### 4. Run the Detection Script
```bash
python detect_speed.py --source your_video.mp4
```

### 5. Output
The processed video with bounding boxes and speed labels will be saved as `output.avi`.

---

## 🗂️ Project Structure

```
intelligent-video-surveillance/
│
├── detect_speed.py          # Main detection and speed tracking script
├── tracker.py               # Vehicle ID tracking / DeepSORT integration
├── calibration.py           # Camera calibration and pixel-to-meter conversion
├── requirements.txt         # Python dependencies
├── models/                  # YOLOv5/YOLOv8 model weights
├── utils/                   # Helper functions
├── output/                  # Processed output videos
└── README.md
```

---

## 🔍 How It Works

```
Video Input
    ↓
Frame Extraction (OpenCV)
    ↓
Vehicle Detection (YOLOv5/YOLOv8)
    ↓
Multi-Object Tracking (DeepSORT / ID Assignment)
    ↓
Speed Estimation
  (pixel displacement × pixel-to-meter ratio × FPS × 3.6 → km/h)
    ↓
Annotated Video Output
```

Speed is estimated using:

```
speed_mps  = pixel_distance × PIXEL_TO_METER × FPS
speed_kmph = speed_mps × 3.6
```

---

## 🎬 Output Demo

> GitHub does not support direct `.avi` playback. Follow the steps below to watch the output video:

**Option 1 — Convert & Upload to GitHub (Recommended)**  
Convert your `.avi` to `.mp4` using this command, then upload to the `output/` folder:
```bash
ffmpeg -i output_video.avi -vcodec libx264 output_video.mp4
```
Then embed it in README like this (replace the URL after uploading):
```
https://github.com/tharunshree13/intelligent-video-surveillance/raw/main/output/output_video.mp4
```

**Option 2 — Upload to YouTube**  
Upload your output video to YouTube and paste the link here:
```
[![Watch Demo](https://img.youtube.com/vi/YOUR_VIDEO_ID/0.jpg)](https://www.youtube.com/watch?v=YOUR_VIDEO_ID)
```

**Option 3 — Download & Watch Locally**  
Download `output/output_video.avi` from this repo and open with VLC Media Player.

*Vehicle detected with bounding box and speed label (km/h) displayed in real time.*

---

## 📊 Results

The system successfully:
- Detects vehicles (class: car) in real-time video frames
- Assigns consistent tracking IDs across sequential frames
- Estimates and displays speed in km/h on each bounding box
- Writes annotated output video for review and law enforcement use

---

## 🚧 Limitations & Future Enhancements

**Current Limitations:**
- Performance may drop in heavy rain, fog, or very low-light conditions
- Occlusion between closely spaced vehicles can affect tracking accuracy
- Speed estimation accuracy depends on camera calibration quality

**Planned Improvements:**
- Integrate ANPR (Automatic Number Plate Recognition) for vehicle identification
- Add night-vision / infrared camera support
- Improve multi-lane tracking in dense traffic scenarios
- Deploy real-time alert system for over-speeding violations
- Cloud dashboard for centralized traffic analytics

---

## 📚 References

- Redmon et al. (2016). *You Only Look Once: Unified, Real-Time Object Detection.* CVPR.
- Bewley et al. (2016). *Simple Online and Realtime Tracking (SORT).* IEEE ICIP.
- Wojke et al. (2017). *Deep SORT: Deep Learning for Multiple Object Tracking.* IEEE ICIP.
- OpenCV — https://opencv.org
- Ultralytics YOLOv5 — https://github.com/ultralytics/yolov5

---

## 👨‍💻 Author

| Name | Roll No | GitHub |
|---|---|---|
| Tharun Shree B | 3592210051 | [@tharunshree13](https://github.com/tharunshree13) |

**Guided by:** Mr. V. Amirthalingam, M.E., Ph.D., Assistant Professor, CSE Dept., VMKV Engineering College, Salem.

---

## 📄 License

This project was developed as an academic mini project at VMKV Engineering College, Salem under Vinayaka Mission's Research Foundation (Deemed to be University).
