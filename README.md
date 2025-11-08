# Driver-Drowsiness-Detection-EE604
# Driver Drowsiness Detection (EE604)

Real-time driver drowsiness detection system using **MediaPipe Face Mesh**, **Eye Aspect Ratio (EAR)**, and **Mouth Aspect Ratio (MAR)**.  
The system monitors eye-closure duration, blink rate, and yawning and triggers an audible alarm if the driver shows signs of fatigue.

---

## 🧠 Core Idea

Fatigue and micro-sleep cause a large percentage of road accidents.  
This project provides a **lightweight, training-free, CPU-friendly** solution that works with a normal webcam or video file and detects:

✅ Prolonged eye closure  
✅ Abnormally low blink rate  
✅ Yawning using adaptive MAR threshold  
✅ Real-time visual overlay and audio alerts  

---

## 🚀 Features

| Feature | Description |
|---------|-------------|
| 👁️ EAR-based Eye Closure | Detects drowsiness when eyes stay closed ≥ 40 consecutive frames |
| 👀 Blink-Rate Monitoring | Flags fatigue when blink rate < 8 per minute |
| 👄 Low-Latency Yawn Detection | Uses adaptive MAR baseline + hysteresis |
| 🔊 Alarm System | Separate alert logic for yawn and general drowsiness |
| 🖥️ Real-Time Processing | 15–30 FPS on CPU, no GPU needed |
| 🎥 Input Modes | Webcam or pre-recorded video |
| 📝 No Training Required | Completely rule-based, explainable, reproducible |

---

## 📌 System Architecture
Video Frame → MediaPipe Face Mesh → EAR / MAR Computation
→ Smoothing + Thresholding → Decision Logic → Alarm + Overlay

---

## 🔧 Tech Stack

| Library | Purpose |
|---------|---------|
| Python 3 | Main language |
| OpenCV | Video capture + drawing overlays |
| MediaPipe | 468-point face mesh landmark detection |
| NumPy | Vectorized EAR / MAR calculations |
| Playsound / Threading | Non-blocking alarm system |

---

## 📥 Installation & Setup

```bash
git clone https://github.com/<username>/Driver-Drowsiness-Detection-EE604.git
cd Driver-Drowsiness-Detection-EE604
pip install -r requirements.txt


python main.py        # Webcam mode
python main.py --video sample.mp4
