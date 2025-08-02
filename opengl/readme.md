

## 💧 Water Molecule Formation Visualization (OpenGL)

This project is a **3D animated simulation** of the formation of a water molecule (H₂O) using **OpenGL and GLUT**. Two **Hydrogen atoms** and one **Oxygen atom** move and combine to form a **water molecule**, with smooth animations and lighting effects. Educational and visually interactive, this project is great for chemistry visualization and computer graphics learning.

---

### 🧪 Features

* 🎥 Smooth animation of atom movement using timer callbacks
* 🌐 3D rendering of atoms using colored spheres
* 💡 Realistic lighting and shading using OpenGL lighting
* 🏷️ Labels for each atom in 3D space
* 🖥️ HUD-style 2D text for messages
* 🔄 Reset the simulation with keyboard input
* 📐 Auto-adjusts view on window resize

---

### 🧱 Atoms Visualization

| Atom     | Color | Radius | Initial Position               |
| -------- | ----- | ------ | ------------------------------ |
| Hydrogen | Red   | 0.3    | -2.0, 0.0, 0.0 & 2.0, 0.0, 0.0 |
| Oxygen   | Blue  | 0.5    | 0.0, 2.0, 0.0                  |

---

### 🚀 How It Works

1. The simulation starts with 2 Hydrogen atoms and 1 Oxygen atom in separate positions.
2. A **timer function** animates the atoms:

   * Hydrogens move inward.
   * Oxygen moves downward.
3. Once the atoms reach close proximity, the `fused` flag is set to `true`, and a **H₂O molecule is rendered**.
4. After fusion:

   * Scene displays celebratory 2D messages:
     `"Water (H2O) molecule created!"`
     `"2 Hydrogen + 1 Oxygen = Life's Elixir 💧"`

---

### 🕹️ Controls

| Key | Action          |
| --- | --------------- |
| `R` | Reset animation |

---

### 📦 Requirements

* OpenGL
* GLUT or FreeGLUT

#### Linux Installation:

```bash
sudo apt-get install freeglut3-dev
```

#### Windows:

* Install **FreeGLUT** and configure your IDE (e.g., Code::Blocks, Visual Studio)

---

### 🧾 File Structure

```
water_molecule.cpp     // Main OpenGL source code
README.md              // Project explanation
```

---

### 🛠️ Compile and Run

#### On Linux:

```bash
g++ water_molecule.cpp -o water_molecule -lGL -lGLU -lglut
./water_molecule
```

#### On Windows (MinGW):

```bash
g++ water_molecule.cpp -o water_molecule -lfreeglut -lopengl32 -lglu32
water_molecule.exe
```

---

### 📸 Screenshots (optional)

> Add screenshots or a GIF showing before and after fusion animation.

---

### 📚 Educational Purpose

This project can be used to demonstrate:

* Basic **OpenGL rendering**
* 3D **transformations** and **lighting**
* **Timer-based animations**
* Use of **HUD elements** in OpenGL
* Chemistry concept visualization

---

### 👩‍💻 Author

**Anisha Kandachar**
Project: *Water Formation — H + H + O = H₂O*


