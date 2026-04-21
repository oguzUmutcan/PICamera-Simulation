# 🚗 Driver Drowsiness Detection System (Raspberry Pi)

A real-time driver monitoring system built with **Python**, **OpenCV**, and **Raspberry Pi**.  
This project detects driver fatigue using face and eye detection and triggers visual and audio alerts.

---

# 📌 Features

- 👁️ Face detection using Haar Cascade
- 👀 Eye detection for drowsiness analysis
- ⚠️ Fatigue detection based on eye closure & face absence
- 🔊 Buzzer alert system
- 🔴🟢 LED indicators:
  - Green → Normal state
  - Red → Drowsiness detected
- 📷 Real-time video processing with PiCamera2
- 🖥️ On-screen warning messages

---

# 🧠 How It Works

The system continuously processes frames from the camera:

1. Detects the driver's face  
2. Searches for eyes in the upper half of the face  
3. Applies logic:
   - ❌ No face detected → Possible head drop
   - ❌ Face detected but no eyes → Possible sleep
   - ✅ Face + eyes detected → Awake

If the system detects fatigue for a defined number of frames, it:
- Activates **buzzer**
- Turns on **red LED**
- Displays warning on screen

---

# 🛠️ Hardware Requirements

- Raspberry Pi (recommended: Pi 4)
- Raspberry Pi Camera Module
- 1x Red LED
- 1x Green LED
- 1x Buzzer
- Resistors (220Ω recommended)
- Jumper wires
- Breadboard

---

## 🔌 GPIO Pin Configuration

| Component   | GPIO Pin |
|------------|----------|
| Green LED  | 23       |
| Red LED    | 17       |
| Buzzer     | 25       |

---

# 💻 Software Requirements

- Python 3
- OpenCV
- Picamera2
- RPi.GPIO

Install dependencies:

```bash
pip install opencv-python
sudo apt install python3-picamera2
````

---

# 📂 Required Files

Make sure the following Haar Cascade XML files are in your project directory:

* `haarcascade_frontalface_default.xml`
* `haarcascade_eye.xml`

You can download them from OpenCV GitHub:
[https://github.com/opencv/opencv/tree/master/data/haarcascades](https://github.com/opencv/opencv/tree/master/data/haarcascades)

---

# ▶️ How to Run

```bash
python3 main.py
```

Press **`q`** to exit the application.

---

# ⚙️ Configuration

You can adjust sensitivity:

```python
YORGUNLUK_ESIGI = 5
```

* Lower value → Faster detection (more sensitive)
* Higher value → More stable detection

---

# ⚠️ Limitations

* Haar Cascade is sensitive to lighting conditions
* May produce false positives in low light or occlusion
* Not as accurate as deep learning-based solutions

---

# 🚀 Future Improvements

* 🔥 Replace Haar Cascade with CNN/DNN models
* 📊 Add EAR (Eye Aspect Ratio) calculation
* 🌙 Improve night-time detection
* 📡 Add logging & remote monitoring
* 🚘 Integrate with real vehicle systems

---

# 👨‍💻 Author

Developed by **Umutcan Oğuz, Azad Bedir, Kadir Gündüz, Yusuf Aksu**

---

# 📄 License

This project is open-source and available under the MIT License.

---

# ⭐ Support

If you like this project, consider giving it a ⭐ on GitHub!
