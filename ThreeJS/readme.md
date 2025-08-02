Thanks for the clarification! Here's a **simplified `README.md`** for your **Three.js-based VR Ganesha project** without WebXR (VR headset support). It includes basic keyboard/mouse movement, two floors, and models hosted on Google Drive.

---

````markdown
# 🙏 VR Ganesha Gallery – Three.js Experience (Without WebXR)

This project is a **3D interactive experience** built using **Three.js**, where users can explore various beautiful **Ganesha idols** across two floors: a ground floor and a first floor. It supports keyboard and mouse movement only — no VR headset required.

## ✨ Features

- 🕉️ Multiple Ganesha idols in `.glb` format
- 🏛️ Two floors: Ground floor and First floor
- 🧍 User movement with keyboard (WASD) and mouse look
- 💡 Realistic lighting and textured environment
- 🎮 Simple navigation without VR/WebXR

## 📦 Ganesha Models (GLB Files)

All Ganesha 3D models used in this project are hosted on Google Drive.  
Download them from the link below and place them in your project folder (`/models` or `/assets`).

🔗 **[Download Ganesha Models from Google Drive](https://drive.google.com/drive/folders/YOUR_DRIVE_FOLDER_ID)**  
*(Replace the above link with your actual folder link)*

## 🚀 How to Run the Project

1. **Clone the repository**

```bash
git clone https://github.com/yourusername/vr-ganesha-gallery.git
cd vr-ganesha-gallery
````

2. **Download the GLB models** from the Google Drive link and place them inside a folder like `/models`.

3. **Start a local server** (Three.js needs a server due to model loading)

```bash
# Using Python 3
python -m http.server
```

Then open your browser and go to:

```
http://localhost:8000
```

## 🎮 Controls

| Action                | Input                                |
| --------------------- | ------------------------------------ |
| Move Forward/Backward | `W` / `S`                            |
| Move Left/Right       | `A` / `D`                            |
| Look Around           | Mouse Movement                       |
| Jump/Go Up Floor      | `Space` (if implemented)             |
| Go Down Floor         | `Shift` or Down Key (if implemented) |

## 🧰 Technologies Used

* [Three.js](https://threejs.org/)
* [GLTFLoader](https://threejs.org/docs/#examples/en/loaders/GLTFLoader)
* Vanilla JavaScript, HTML, and CSS

## 🙏 Credits

* Ganesha models: [Sketchfab](https://sketchfab.com/), custom uploads
* Textures: [Poly Haven](https://polyhaven.com/), [AmbientCG](https://ambientcg.com/)
* Movement & scene logic: custom using Three.js and PointerLockControls

## 📜 License

This project is open-source and licensed under the **MIT License**.

---

*“Vakratunda Mahakaya Suryakoti Samaprabha…”*
May this virtual space bring blessings, creativity, and joy to all who visit. 🙏

```

---

Let me know if you'd like:

- A sample `index.html` or `main.js` structure
- Screenshot or video placeholders in the README
- Model viewer preview

I'm happy to generate those too.
```
