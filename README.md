# Virtual Hand Gesture Steering Control

A Python project that uses a trained deep learning model to recognize hand gestures (left, right, straight, stop) in real-time and control a car game (or any application) via simulated key presses. Gesture detection is powered by a TensorFlow/Keras CNN, and real-time video processing is done with OpenCV and MediaPipe.

---

## 🚀 Features

- **Real‑time gesture recognition** (left, right, straight, stop)
- **Deep Learning model** (custom CNN trained on your own dataset)
- **Smooth control** using frame smoothing to avoid flicker
- **Simulated key presses** with `pyautogui` (W/A/S/D or arrows)
- **No external YOLO/third‑party weights** required
- Configurable Region of Interest (ROI) for hand position

---

## 📦 Requirements

- Python 3.7+
- TensorFlow
- OpenCV (`opencv-python`)
- MediaPipe
- PyAutoGUI

Install dependencies via pip:

```bash
pip install tensorflow opencv-python mediapipe pyautogui
```

---

## 🗂 Project Structure

```text
VirtualHandSteering/
├── gesture_model.h5       # Trained Keras model file
├── README.md              # This documentation
├── collecting_dataset.ipynb/               # Your collected images (left/right/straight/stop)
├── cleaning &model_creation.ipynb/         # Script to preprocess, train, and save the model
└── final.ipynb    # Real-time gesture prediction & key control
```

---

## 🛠 Installation & Setup

1. **Clone the repository**:
   ```bash
   ```

git clone https://github.com/parimalamurugan123/virtual_steering.git
cd virtual_steering


````

2. **Install dependencies**:
```bash
pip install tensorflow opencv-python mediapipe pyautogui
````

3. **Place your trained model**
   - Ensure `gesture_model.h5` is in the project root.

---

## 🏋️‍♂️ Training the Model

If you need to retrain the model on your own data:

```bash
python train_model.py
```

- Collect images into `dataset/left`, `dataset/right`, `dataset/straight`, `dataset/stop`.
- The script will preprocess, split (80/20), train a CNN, and save `gesture_model.h5`.

---

## 🎥 Real‑Time Gesture Control

Run the main control script:

```bash
python realtime_control.py
```

- Make sure your webcam is connected.
- Use gestures in front of the camera:
  - **Left**: Turn left key (A)
  - **Right**: Turn right key (D)
  - **Straight**: Go forward key (W)
  - **Stop**: Release controls (S)
- Press `q` to exit.

---

## ⚙️ Configuration

- **ROI**: Adjust the cropping coordinates in `realtime_control.py` to match your camera setup.
- **Smoothing**: Modify `SMOOTHING_THRESHOLD` in the script to control how many frames a gesture must persist before triggering.
- **Key Mapping**: Change the key assignments in the `KEYS` dictionary if your game uses different controls.

---

## 🔧 Troubleshooting

- **Frame Lag**: Reduce camera resolution or increase `SMOOTHING_THRESHOLD`.
- **Incorrect Predictions**: Retrain with more/augmented data, ensure consistent lighting.
- **Key Presses Not Working**: Verify `pyautogui` can send keys in your environment; test `pyautogui.press('a')` separately.



---

## 🙏 Acknowledgments

- [OpenCV](https://opencv.org/)
- [MediaPipe](https://mediapipe.dev/)
- [TensorFlow](https://www.tensorflow.org/)
- [PyAutoGUI](https://pyautogui.readthedocs.io/)

---
## OUTPUT




Made with ❤️ by Your parimala

