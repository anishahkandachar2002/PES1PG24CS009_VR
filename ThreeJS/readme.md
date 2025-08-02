
````markdown
# 🕉️ VR Ganesha Gallery – Three.js Project (No VR Headset Required)

This is a **Three.js-based virtual experience** showcasing multiple forms of **Lord Ganesha** in a peaceful 3D environment. It includes two floors (ground + first floor), user movement using keyboard and mouse, and interactive viewing of `.glb` Ganesha models.

📍 **Project Repository:**  
[https://github.com/anishahkandachar2002/PES1PG24CS009_VR/tree/main/ThreeJS](https://github.com/anishahkandachar2002/PES1PG24CS009_VR/tree/main/ThreeJS)

## ✨ Key Features

- 🛕 Multiple Ganesha idols (loaded as `.glb` models)
- 🏠 Ground and First Floor layout
- 🎮 Keyboard + Mouse navigation (PointerLockControls)
- 💡 Ambient lighting, textures, and realistic environment
- 🚫 No VR headset required – accessible via regular web browser

## 📦 3D Model Download

The `.glb` files used in this project are hosted on Google Drive.

📥 **[Download Ganesha Models](https://drive.google.com/drive/folders/1Bl3gybprbPlgW9o0im8XHwTPElCABRNg?usp=sharing)**  
> After downloading, place them inside the `main folder.  


## 🚀 Running the Project Locally

1. **Clone the repository:**

```bash
git clone https://github.com/anishahkandachar2002/PES1PG24CS009_VR.git
cd PES1PG24CS009_VR/ThreeJS
````

2. **Start a local server** (required to load models via Three.js)

```bash
# For Python 3
python -m http.server
```

Then open your browser at:
[http://localhost:8000](http://localhost:8000)

## 🎮 Controls

| Action        | Key/Input                        |
| ------------- | -------------------------------- |
| Move Forward  | `W`                              |
| Move Backward | `S`                              |
| Move Left     | `A`                              |
| Move Right    | `D`                              |
| Look Around   | Move Mouse                       |
| Switch Floor  | Use teleport/stairs (if enabled) |

## 🧰 Tech Stack

* [Three.js](https://threejs.org/)
* `GLTFLoader` for loading 3D models
* `PointerLockControls` for first-person movement
* HTML, CSS, JavaScript (Vanilla)

## 🙏 Credits

* Ganesha 3D models: [Sketchfab](https://sketchfab.com/) / Google Drive
* Textures: [AmbientCG](https://ambientcg.com/), [Poly Haven](https://polyhaven.com/)
* Scene & control logic: Custom implementation in Three.js

## 📜 License

This project is open-source and available under the **MIT License**.

---

*“Vakratunda Mahakaya Suryakoti Samaprabha…”*
May Lord Ganesha guide your journey through code and creativity 🙏
