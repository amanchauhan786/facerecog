<img width="439" height="213" alt="image" src="https://github.com/user-attachments/assets/a41d9853-b09e-4f79-b054-2d0dde7e2176" />



````markdown
# Real-Time Face Recognition System

A real-time face recognition system built with Python and OpenCV. It can identify known individuals from a live webcam feed and label them with their names. The system is designed to be simple to set up and easy to expand with new faces.

![Face Recognition Preview](path-to-your-gif-or-screenshot)  
Caption: The system identifying a known face from a webcam feed.

---

## 📋 Table of Contents

- [Features](#-features)  
- [How It Works](#-how-it-works)  
- [Tech Stack](#-tech-stack)  
- [Getting Started](#-getting-started)  
- [How to Use](#-how-to-use)  
- [Project Structure](#-project-structure)  
- [Future Improvements](#-future-improvements)  

---

## ✨ Features

- Real-Time Recognition: Identifies faces instantly from a live video stream.  
- High Accuracy: Uses a state-of-the-art face recognition library.  
- Easy Enrollment: Simple script to add new individuals to the known faces database.  
- Dynamic Labeling: Draws a bounding box and displays the recognized person's name.  
- Efficient: Processes video frames quickly to maintain a smooth live feed.  

---

## 🧠 How It Works

The system operates in two main phases:

### 1. Encoding (Data Preparation)
- EncodeGenerator.py scans the Images folder.  
- Each image is processed to generate a unique 128-point facial encoding.  
- Encodings and names are saved to EncodeFile.p using pickle — this acts as the database of known faces.  

### 2. Recognition (Live Feed)
- main.py loads the encodings from EncodeFile.p.  
- Captures frames from the webcam in real-time.  
- Detects all faces in each frame and computes their encodings.  
- Matches the encodings against known faces.  
- Draws a rectangle around recognized faces and displays their names.  

---

## 🛠️ Tech Stack

- Python: Core language  
- OpenCV (cv2): Webcam feed and drawing rectangles on video  
- face_recognition: High-level library for face detection and recognition  
- dlib: Core face recognition model  
- NumPy: Handling numerical operations and image data arrays  
- Pickle: Serializing and saving face encodings  

---

## 🚀 Getting Started

### Prerequisites

- Python 3.6+  
- Working webcam  
- May require CMake for installing dlib  

### Installation Steps

```bash
git clone https://github.com/amanchauhan786/facerecog.git
cd facerecog
````

Set up a virtual environment:

```bash
# Windows
python -m venv venv
.\venv\Scripts\activate

# macOS/Linux
python3 -m venv venv
source venv/bin/activate
```

Install required packages:

```bash
pip install opencv-python cmake dlib face_recognition numpy
```

---

## 🗣️ How to Use

### 1. Add Your Images (Enroll New Faces)

* Place .jpg or .png images in the Images folder.
* Name the files as the person's name, e.g., Elon Musk.jpg.

### 2. Generate the Encodings File

```bash
python EncodeGenerator.py
```

* Only run this after adding or changing images.

### 3. Run the Face Recognition

```bash
python main.py
```

* A window will pop up showing the webcam feed.
* Known faces will be labeled.
* Press q to quit.

---

## 📁 Project Structure

```
facerecog/
├── Images/
│   ├── Elon Musk.jpg
│   ├── Jeff Bezos.jpg
│   └── ... (add your images here)
├── EncodeGenerator.py   # Script to encode known faces
├── main.py              # Main script to run the live recognition
└── EncodeFile.p         # Generated file with face encodings
```

---

## 🔮 Future Improvements

* Attendance System: Log recognized individuals with timestamps.
* GUI: Build a user interface with Tkinter or PyQt.
* Performance Optimization: Implement threading for better frame rates.
* "Unknown" Person Detection: Label faces not in the database as "Unknown".


```
