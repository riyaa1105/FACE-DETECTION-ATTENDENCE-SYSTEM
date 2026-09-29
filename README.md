# 🎓 Face Detection Attendance System

[![Python](https://img.shields.io/badge/Python-3.9%2B-blue.svg)](https://www.python.org/)
[![OpenCV](https://img.shields.io/badge/OpenCV-4.10%2B-green.svg)](https://opencv.org/)
[![License](https://img.shields.io/badge/License-MIT-yellow.svg)](LICENSE)
[![Status](https://img.shields.io/badge/Status-Active-success.svg)]()

A comprehensive **Face Recognition-based Attendance Management System** built with Python, OpenCV, and Tkinter. This system automates attendance tracking using real-time facial recognition, eliminating manual processes and providing slot-based attendance tracking and report generation.

---

## 📋 Table of Contents

- [Features](#-features)
- [Technology Stack](#-technology-stack)
- [System Requirements](#-system-requirements)
- [Installation](#-installation)
- [Usage Guide](#-usage-guide)
- [Project Structure](#-project-structure)
- [How It Works](#-how-it-works)
- [Troubleshooting](#-troubleshooting)
- [Contributing](#-contributing)
- [License](#-license)
- [Author](#-author)

---

## ✨ Features

### 👤 Student Registration & Image Capture
- **Registration**: Captures enrollment number, student name, roll number, and division.
- **Auto Image Capture**: Captures 50+ face samples automatically via camera feed using OpenCV Haar Cascade.

### 🧠 Model Training
- **LBPH Recognizer**: Uses Local Binary Patterns Histograms (LBPH) classifier from `opencv-contrib-python`.
- **Single-Click Training**: Trains model on registered images and exports `Trainner.yml`.

### ⏱️ Automated Attendance & Time Slots
- **Slot Management**: Organizes attendance into 7 pre-defined time slots (7:00 AM to 2:00 PM).
- **Subject-Wise Tracking**: Keeps separate attendance records per subject.
- **Voice Feedback**: Uses `pyttsx3` text-to-speech for audible confirmation.

### 📊 Attendance Viewing & Maintenance
- **Data Viewer**: Displays total classes held, attendance per student, and percentage calculations.
- **Data Cleanup Script**: Built-in utility (`cleanup_old_data.py`) to safely clear old datasets and models.

---

## 🛠️ Technology Stack

| Technology / Package | Version / Purpose |
|----------------------|-------------------|
| **Python 3.9+** | Core Programming Language |
| **OpenCV (`opencv-contrib-python`)** | Computer vision and LBPH Face Recognizer |
| **Tkinter** | Native Python GUI framework |
| **Pandas** | Data processing & CSV attendance calculation |
| **NumPy** | Numerical computations for image matrix transformation |
| **Pillow (PIL)** | Image loading and GUI rendering |
| **pyttsx3** | Text-to-speech voice notifications |
| **openpyxl** | Excel file export support |

---

## 💻 System Requirements

### Hardware
- **Webcam**: Integrated or USB external camera (720p or better recommended)
- **RAM**: Minimum 4 GB (8 GB recommended)
- **Storage**: 500 MB available disk space

### Software
- **OS**: Windows 10/11, macOS, or Linux
- **Python**: Version 3.9 or higher

---

## 📦 Installation

### 1. Clone the Repository
```bash
git clone https://github.com/riyaa1105/FACE-DETECTION-ATTENDENCE-SYSTEM.git
cd FACE-DETECTION-ATTENDENCE-SYSTEM
```

### 2. Set Up a Virtual Environment (Optional but Recommended)
```bash
# Windows
python -m venv venv
venv\Scripts\activate

# macOS / Linux
python3 -m venv venv
source venv/bin/activate
```

### 3. Install Dependencies
```bash
pip install -r requirements.txt
```

---

## 🚀 Usage Guide

### Launching the Application
Run the main entrypoint script:
```bash
python attendance.py
```

### Step-by-Step Workflow

#### 1️⃣ **Register New Student**
1. Click **"Register New Student"**.
2. Enter student details: Division, Enrollment No, Roll No, and Name.
3. Click **"Take Image"** — the webcam will automatically capture face images.

#### 2️⃣ **Train the Model**
1. Click **"Train Image"**.
2. The system reads all captured images and updates `TrainingImageLabel/Trainner.yml`.

#### 3️⃣ **Take Attendance**
1. Click **"Take Attendance"**.
2. Select or enter the subject name.
3. The camera opens and scans faces in real-time. Recognized students have their attendance logged for the current time slot.

#### 4️⃣ **View Attendance Reports**
1. Click **"Show Attendance"**.
2. Input the subject name to generate and view attendance percentages and attendance sheets.

#### 🧹 **Cleaning Up Old Data**
To clear old training images, models, or attendance logs:
```bash
python cleanup_old_data.py
```

---

## 📁 Project Structure

```
FACE-DETECTION-ATTENDENCE-SYSTEM/
│
├── attendance.py                     # Main application entry point & GUI dashboard
├── automated_attendance.py           # Real-time face detection & slot-based attendance logic
├── take_image.py                     # Student registration & image dataset collection
├── train_image.py                    # LBPH face recognizer model training script
├── show_attendance.py                # Attendance report viewer & analytics GUI
├── cleanup_old_data.py               # Maintenance script for clearing datasets/models
│
├── haarcascade_frontalface_default.xml # Haar Cascade xml file for face detection
├── requirements.txt                  # Python package requirements
├── AMS.ico                           # Application window icon
├── UI_DESIGN_INFO.md                 # GUI design reference documentation
├── README.md                         # Project documentation
│
├── TrainingImage/                    # Folder containing captured student face samples
├── TrainingImageLabel/               # Contains trained classifier model (Trainner.yml)
├── StudentDetails/                   # Contains student details CSV database
└── Attendance/                       # Attendance CSV records organized by subject
```

---

## 🔧 How It Works

1. **Face Detection**: Uses OpenCV's `HaarCascade Frontal Face` model (`haarcascade_frontalface_default.xml`) to draw bounding boxes around faces in real-time video frames.
2. **Feature Extraction**: Converts detected face regions into grayscale and extracts Local Binary Pattern Histograms.
3. **Classification & Matching**: Compares input face histogram against `Trainner.yml`. If confidence meets threshold criteria, student identity is confirmed.
4. **Attendance Logging**: Matches current system time to pre-defined time slots and appends attendance records into Pandas DataFrames and CSV files.

---

## ⚠️ Troubleshooting

| Problem | Cause | Solution |
|---------|-------|----------|
| `cv2.face` module missing | Using standard `opencv-python` instead of contrib | Run `pip install opencv-contrib-python` |
| Camera cannot open | Camera in use or missing drivers | Ensure webcam is connected and closed in other applications |
| Recognition confidence low | Poor lighting or insufficient samples | Ensure good lighting and register 50+ image samples |

---

## 🤝 Contributing

Contributions, issues, and feature requests are welcome!
1. Fork the Project (`git checkout -b feature/NewFeature`)
2. Commit your Changes (`git commit -m 'Add NewFeature'`)
3. Push to the Branch (`git push origin feature/NewFeature`)
4. Open a Pull Request

---

## 📄 License

Distributed under the **MIT License**. See `LICENSE` for details.

---

## 👨‍💻 Author

**Raj Jadav**
- **GitHub**: [@rajjadav007](https://github.com/rajjadav007)
- **Repository**: [FACE-DETECTION-ATTENDENCE-SYSTEM](https://github.com/rajjadav007/FACE-DETECTION-ATTENDENCE-SYSTEM)

---

<div align="center">
  ⭐ Star this repository if you find it helpful!
</div>