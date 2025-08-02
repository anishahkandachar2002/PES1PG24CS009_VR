# PES1PG24CS009_VR PROJECT

## 🎨 OpenGL & Three.js Projects

This repository showcases multiple interactive 3D projects built using **OpenGL (C++)** and **Three.js (JavaScript)**. These projects demonstrate real-time 3D graphics concepts for educational and immersive experiences.

Special thanks to PES University and Aditya Sir for providing the project opportunity and valuable evaluation.
---

### 🔬 H2O Formation — OpenGL

An animated simulation of **water molecule formation (H₂O)** using OpenGL.

* Smooth animation of 2 Hydrogens and 1 Oxygen moving and fusing.
* Real-time lighting, labeled atoms, and rotation.
* Displays educational HUD messages upon successful molecule formation.
* Reset the simulation with the `R` key.
* Ideal for chemistry visualizations and OpenGL learning.

Compile with:

```bash
g++ water_molecule.cpp -o water_molecule -lGL -lGLU -lglut
```

---

### 🛕 VR Ganesha Temple — Three.js

A **web-based VR gallery** using Three.js to explore various forms of Lord Ganesha in a virtual temple environment.

* Includes user navigation, floor transitions, and interactive camera controls.
* Loads .glb models hosted externally (e.g., Google Drive).
* Runs directly in modern browsers.
* Great for cultural heritage experiences and WebGL/Three.js learning.

Open directly in your browser or use a local server:

```bash
npx serve .
```

---

### 🛠 Requirements

✅ **OpenGL Project:**

* C++ compiler with OpenGL & GLUT libraries installed.
* Runs on Linux, Windows, or Mac.

✅ **Three.js Project:**

* Modern web browser (Chrome, Firefox, Edge, etc.).
* Optional: VS Code with Live Server for development.

---

### 👩‍💻 Author

Developed by **Anisha Kandachar**
Exploring interactive 3D graphics with OpenGL and Three.js.

---


