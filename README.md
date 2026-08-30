<img width="1212" height="860" alt="Image" src="https://github.com/user-attachments/assets/9903bdd2-d616-4a71-b48c-abf979829912" />
<img width="1440" height="900" alt="Image" src="https://github.com/user-attachments/assets/e02067f8-8291-47c8-a21c-3596bd208bd5" />
<img width="1440" height="900" alt="Image" src="https://github.com/user-attachments/assets/820830a9-7d52-43f6-8b0c-9eb0fc42b5f6" />

# 🚗 Real-Time Parking Space Counter

An automated computer vision system built with Python and OpenCV that detects parking slot occupancy and displays available spaces in real time.

---

## 📌 Overview

This project provides a lightweight alternative to resource-heavy deep learning models for parking space management. By combining manual slot mapping with image processing techniques (adaptive thresholding, blurring, and pixel dilation), it determines spot availability based on non-zero pixel density inside predefined regions.

---

## 📸 Demo & Output

*(Make sure your output is saved in the root directory as 'CarParkPos')*

![Parking Space Counter Output](CarParkPos)

---

## 🛠️ Features

- **Interactive Slot Selector:** Click-to-add and right-click-to-remove parking slot positions.
- **Position Persistence:** Automatically saves and loads slot coordinates using Python's `pickle` module.
- **Video Feed Looping:** Automatically resets video playback for seamless real-time monitoring.
- **Visual Feedback:** 
  - 🟩 **Green Box:** Slot is free (pixel count < 900).
  - 🟥 **Red Box:** Slot is occupied (pixel count ≥ 900).
  - 📊 **Real-time Counter:** Live banner displaying available spots over total capacity (e.g., `Free: 12/69`).

---

## 📁 Repository Structure

```text
├── carPark.mp4              # Sample input video feed
├── carParking.png            # Reference image used for marking slots
├── CarParkPos                # Pickled file containing slot coordinates
├── ParkingSpacePicker.py     # Script to annotate parking slots
├── main.py                   # Real-time detection & counter script
└── README.md                 # Project documentation

### 📝 Step-by-step process to complete this project

**⚙️ Prerequisites & Installation**

1. Clone the Repository
Bash
git clone [https://github.com/rajesh23092023/parking-space-counter.git](https://github.com/rajesh23092023/parking-space-counter.git)
cd parking-space-counter

2. Set Up a Virtual Environment (Optional but Recommended)
Bash
# macOS/Linux
python3 -m venv .venv
source .venv/bin/activate
# Windows
python -m venv .venv
.venv\Scripts\activate

3. Install Dependencies
Bash
pip install opencv-python cvzone numpy

**🚀 How to Run the Project**
Step 1: Define Parking Slots (Optional if CarParkPos exists)
If you want to create or update parking slot coordinates:

Bash
python ParkingSpacePicker.py
Left Click: Place a new parking bounding box at the cursor position.

Right Click: Click inside any existing box to delete it.

Your marked coordinates are saved automatically to CarParkPos.

Step 2: Run Real-Time Space Detection
Run the main tracking application:

Bash
python main.py
