# 🖐️ Gesture-Based Volume Control using OpenCV and MediaPipe

This project is a Python-based tool that lets you control your system volume **using hand gestures** via a webcam. It tracks the distance between your thumb and index finger and adjusts the volume accordingly.

It uses:
- **OpenCV** for real-time video processing
- **MediaPipe** (through a custom `HandTrackingModule`) for hand landmark detection
- **pycaw** for interacting with Windows system audio settings

---

## 🔧 Features

- Control system volume using hand gestures.
- Real-time FPS (Frames Per Second) monitoring.
- Dynamic volume bar and percentage display.
- Visual feedback (color changes when muted).
- Modular and reusable HandTracking logic in a separate module.

---

## 📷 How It Works

- The webcam captures your hand using OpenCV.
- `HandTrackingModule` (built on MediaPipe) detects hand landmarks.
- It calculates the distance between the **thumb tip (landmark 4)** and the **index finger tip (landmark 8)**.
- This distance is mapped to the system's volume range using `pycaw`.
- Visual elements are displayed in the OpenCV window for interaction and feedback.

---

## 🧩 Requirements

To run this project, make sure you have the following Python libraries installed:

### 📄 `requirements.txt`

```
opencv-python
mediapipe
pycaw
comtypes
numpy
```

You can install them using:

```bash
pip install -r requirements.txt
```

---

## 🗂️ Project Structure

```
├── HandTrackingModule.py       # Custom hand tracking module (MediaPipe-based)
├── volumeControl.py            # Main script to run the volume control
├── requirements.txt            # List of required libraries
├── README.md                   # This documentation
```

---

## 🚀 How to Run

1. Clone or download this repository.
2. Connect your webcam.
3. Install the dependencies:

   ```bash
   pip install -r requirements.txt
   ```

4. Run the script:

   ```bash
   python volumeControl.py
   ```

> 📌 Tip: If your webcam is not working, try changing `cv2.VideoCapture(1)` to `cv2.VideoCapture(0)` in the code.

---

## 🖥️ Platform Support

- ✅ Windows (required for `pycaw`)
- ❌ Not supported on Linux/macOS (due to Windows-specific volume control library)

---

## 🙌 Acknowledgements

- [MediaPipe](https://google.github.io/mediapipe/) by Google for robust hand tracking
- [OpenCV](https://opencv.org/) for computer vision tools
- [pycaw](https://github.com/AndreMiras/pycaw) for Windows audio control

---

## 👨‍💻 Author

Made with ❤️ by **[Harsh Dixit]**  
Built as an extension of tutorial concepts, enhanced with a **custom-built HandTrackingModule** for modularity and reusability.
