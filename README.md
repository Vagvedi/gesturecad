# 🧊 Voxel Architect v4.1  
### Gesture-Driven 3D Construction System (Browser-Native)

Voxel Architect is an experimental, real-time voxel modeling environment controlled entirely through **hand gestures**, without a mouse, keyboard, or controller.

The system combines **computer vision**, **gesture intent recognition**, and **GPU-accelerated 3D rendering** to enable spatial construction directly inside the browser.

---

## 🚀 What This Project Does

- Tracks both hands in real time using the webcam  
- Interprets **human intent** (build, erase, grab, rotate) via gesture holds  
- Allows users to **construct 3D voxel structures** in mid-air  
- Renders everything using **WebGL** with live visual feedback  

This is **not** a UI demo — it is a **human–computer interaction system**.

---

## 🎮 Gesture Controls

| Gesture | Action |
|------|------|
| Pinch + Point | Build voxels |
| Pinch + Drag | Axis-locked voxel drawing |
| Pinch + Palm | Erase voxels |
| Fist (hold) | Grab & move structure |
| Two Palms (hold) | Rotate entire structure |
| Two Fists (hold) | Hard reset |

Visual HUD indicators confirm intent locking and gesture state.

---

## 🧠 System Architecture (High Level)

### 1️⃣ Input Layer  
- Webcam video stream  
- MediaPipe Hands (21 landmarks per hand)

### 2️⃣ Interpretation Layer  
- Temporal landmark smoothing  
- Custom gesture classifiers (pinch, fist, palm)  
- Hold-based intent detection to avoid false positives  

### 3️⃣ Construction Layer  
- Grid-quantized voxel placement  
- Sketch-then-commit pipeline  
- Memory-safe voxel indexing  

### 4️⃣ Rendering Layer  
- WebGL via Three.js  
- Emissive voxel materials  
- Wireframe previews & crosshair targeting  

---

## 🛠️ Technologies Used

- **HTML5** – Runtime container and media pipeline  
- **CSS3** – HUD styling and layered visual hierarchy  
- **JavaScript (ES6)** – Core logic, gesture interpretation, state handling  
- **MediaPipe Hands** – Real-time computer vision hand tracking  
- **Three.js** – GPU-accelerated 3D rendering  

---

## 📄 Why This Is a Single-File Project

This project is intentionally implemented as a **single HTML file**.

### Rationale:
- Designed as a **browser-native real-time system**, not a traditional web app  
- Avoids bundlers and frameworks to reduce latency  
- Easier to deploy, test, and demo (one file = zero setup)  
- All subsystems are logically separated **within the file**, even if physically colocated  

This approach is common in:
- WebGL experiments  
- Computer vision demos  
- Research prototypes  
- Hackathon and R&D environments  

The architecture is modular **by responsibility**, not by file count.

---

## ▶️ How to Run

> ⚠️ Camera access requires a local HTTP server.

### Option 1: VS Code Live Server
1. Open the folder in VS Code  
2. Right-click `index.html` → **Open with Live Server**  
3. Allow camera permissions in the browser  

### Option 2: Python
```bash
python -m http.server
