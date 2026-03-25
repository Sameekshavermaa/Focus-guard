# 🎯 FocusGuard — Anti Doom Scroll

> A webcam-powered attention monitor that triggers a focus intervention video when you look away for too long — built with MediaPipe Face Mesh.

![FocusGuard](https://img.shields.io/badge/Status-Live-00ffe0?style=flat-square) ![HTML](https://img.shields.io/badge/Built%20With-HTML%20%2F%20CSS%20%2F%20JS-00ffe0?style=flat-square) ![MediaPipe](https://img.shields.io/badge/AI-MediaPipe%20Face%20Mesh-00ffe0?style=flat-square) ![License](https://img.shields.io/badge/License-MIT-00ffe0?style=flat-square)

![image alt](https://github.com/Sameekshavermaa/Focus-guard/blob/5a5b615e1f9b7e49b307e80263e0ab76c1c61c3a/Screenshot%202026-03-22%20at%2016.12.02.png)
![image alt](https://github.com/Sameekshavermaa/Focus-guard/blob/4f956ed333a15a44d0e46524bec6616766c40794/Screenshot%202026-03-22%20at%2016.12.27.png)
![image alt](https://github.com/Sameekshavermaa/Focus-guard/blob/30d46f72631e8554b0c75565d510c960aaf69967/Screenshot%202026-03-22%20at%2016.12.42.png)

---

## 🚀 Live Demo

**[▶ Try FocusGuard Live] **https://focus-guard-zeta.vercel.app/**

---

## 📸 What It Does

FocusGuard is a browser-based anti-doom-scrolling tool that uses your webcam and AI face tracking to monitor your attention in real time.

- 👁 **Tracks your gaze** using head pose estimation and iris detection
- ⏱ **Starts a countdown** the moment you look away
- 🎬 **Triggers a full-screen intervention video** if you stay distracted too long
- 📊 **Tracks your session stats** — focus %, away time, intervention count
- 🔒 **100% private** — no data ever leaves your browser

---

## ✨ Features

| Feature | Details |
|---|---|
| 🧠 AI Face Tracking | MediaPipe Face Mesh with 468 landmarks |
| 👀 Gaze Detection | Head pose + iris position + eye openness |
| ⏱ Away Timer | Configurable 5–30 second threshold |
| 🎬 Intervention Video | Upload your own or use a breathing placeholder |
| 🔔 Sound Alert | 3-beep warning before video triggers |
| 📊 Session Stats | Focus %, session time, interventions, detection rate |
| 🎛 Sensitivity Modes | Low / Medium / High debounce control |
| 📦 Face Bounding Box | Live corner-bracket overlay on detected face |
| ⚙️ Calibration Screen | Configure everything before starting |
| 🔒 Fully Local | Zero backend, zero data collection |

---

## 🛠 Tech Stack

- **HTML / CSS / Vanilla JavaScript** — no frameworks, no build tools
- **[MediaPipe Face Mesh](https://google.github.io/mediapipe/solutions/face_mesh)** — real-time 468-point 3D facial landmark detection
- **Web APIs** — `getUserMedia`, `AudioContext`, `Canvas`, `File API`
- **Google Fonts** — Syne + Space Mono

---

## 🧠 How Detection Works

FocusGuard uses **MediaPipe Face Mesh** running at ~15fps and analyses 3 signals to determine if you're looking at the screen:

### 1. Head Turn (Horizontal)
Compares the nose tip position relative to the midpoint between both eye corners. If the nose shifts too far left or right, the head is turned away.

### 2. Head Tilt (Vertical)
Measures the nose Y position relative to the forehead-to-chin span. A dropped chin (looking down at phone, for example) is flagged as distracted.

### 3. Eye Openness
Measures the vertical distance between upper and lower eyelid landmarks. Fully closed eyes (sleeping, looking down) trigger the distracted state.

### Debounce Logic
To prevent false triggers from blinks or micro-movements, the app requires **N consecutive frames** in the same state before switching:

| Sensitivity | Frames Required |
|---|---|
| Low | 20 frames |
| Medium | 12 frames |
| High | 5 frames |

### Dismissal Logic
While the intervention overlay is active, returning your gaze fills a **"return bar"**. It requires **15 consecutive focused frames** before auto-dismissing — preventing accidental glance-aways from closing it.

---

## 📁 File Structure

```
focusguard/
├── index.html      # Entire app — HTML + CSS + JS in one file
└── README.md       # This file
```

---

## ▶ Running Locally

No install needed. Just open the file:

```bash
# Option 1 — Python local server (recommended)
python3 -m http.server 8080
# Then open: http://localhost:8080

# Option 2 — VS Code
# Install the "Live Server" extension and click "Go Live."

# Option 3 — Direct open (may not work in all browsers)
# Double-click index.html
```

> ⚠️ Camera access requires either `localhost` or an `https://` URL. Direct file opening (`file://`) may block webcam access in some browsers.

---

## 🚀 Deploying to GitHub Pages

1. Push `index.html` to a public GitHub repository
2. Go to **Settings → Pages**
3. Set source to **main branch / root**
4. Your app will be live at `https://YOUR_USERNAME.github.io/REPO_NAME/`

GitHub Pages automatically serves over HTTPS, so webcam access works out of the box.

---

## ⚙️ Configuration Options

All settings are available on the **Calibration Screen** before starting, and sensitivity can be changed live:

| Setting | Range | Default |
|---|---|---|
| Away Timer Threshold | 5s – 30s | 10s |
| Detection Sensitivity | Low / Medium / High | Medium |
| Intervention Video | Any local video file | Breathing placeholder |
| Sound Alert | On / Off | On |

---

## 🖥 Browser Support

| Browser | Support |
|---|---|
| ✅ Chrome | Full support |
| ✅ Edge | Full support |
| ⚠️ Firefox | Partial (MediaPipe may be slower) |
| ⚠️ Safari | Limited (getUserMedia restrictions) |

**Recommended: Google Chrome or Microsoft Edge**

---

## 🔒 Privacy

- All processing happens **entirely in your browser**
- Webcam frames are **never uploaded or stored**
- No analytics, no tracking, no cookies
- No internet connection needed after the page loads (CDN assets cached)

---

## 📄 License

MIT License — free to use, modify, and distribute.

---

## 🙌 Acknowledgements

- [MediaPipe](https://mediapipe.dev/) by Google for the Face Mesh model
- [Syne](https://fonts.google.com/specimen/Syne) + [Space Mono](https://fonts.google.com/specimen/Space+Mono) via Google Fonts

---

<p align="center">Built to fight the scroll. Stay focused. 🎯</p>



