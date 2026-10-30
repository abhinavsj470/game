# 🌌 Cyber Horizon 3D: Neon Tunnel Runner & Shooter

[![Three.js](https://img.shields.io/badge/Three.js-r128-black?style=for-the-badge&logo=three.js)](https://threejs.org/)
[![JavaScript](https://img.shields.io/badge/JavaScript-ES6+-F7DF1E?style=for-the-badge&logo=javascript&logoColor=black)](https://developer.mozilla.org/en-US/docs/Web/JavaScript)
[![HTML5 / Canvas](https://img.shields.io/badge/HTML5-Canvas_WebGL-E34F26?style=for-the-badge&logo=html5&logoColor=white)](https://developer.mozilla.org/en-US/docs/Web/API/Canvas_API)
[![Web Audio API](https://img.shields.io/badge/Web_Audio-Synthesizer-8A2BE2?style=for-the-badge)](https://developer.mozilla.org/en-US/docs/Web/API/Web_Audio_API)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg?style=for-the-badge)](https://opensource.org/licenses/MIT)

> A high-speed, browser-based 3D cyberpunk space runner and tunnel shooter built purely with **Three.js** and procedural **Web Audio API** sound synthesis in a zero-dependency, single-file bundle.

---

## ⚡ Overview

**Cyber Horizon 3D** plunges the player into an infinite synthwave hyper-tunnel. Maneuver a futuristic vector interceptor through hostile cyber-space, dodge monolithic neon hazards, intercept crimson hunter drones, collect power-up cores, and trigger devastating screen-clearing EMP blastwaves.

Everything—geometry generation, lighting, dynamic particle systems, collision routines, and polyphonic sound synthesis—is self-contained with no external 3D asset downloads or audio file dependencies.

---

## ✨ Features

- **Infinite 3D Synthwave Hyper-Tunnel**:
  - Procedurally generated cylindrical lattice with alternating neon wireframes and depth-fade fog.
  - Multi-layered starfield with dynamic hyper-drive warp streak effects.
- **Dynamic Camera Modes**:
  - Seamless toggle between **Chase View (Third-Person)**, **Cockpit View (First-Person)**, and **Wide Tactical Orbit**.
  - Interactive mouse/touch orbit control with smooth interpolation (`slerp`/`lerp`).
- **Enemies & Obstacles**:
  - **Hunter Drones**: Hostile crimson interceptors that dart across tunnel rings.
  - **Swarm Scouts**: High-frequency golden targets offering score multipliers.
  - **Neon Monoliths**: Indestructible barrier slabs requiring swift roll and dodge maneuvers.
- **Dynamic Power-Up Cores**:
  - 🟢 **Nano Hull Repair**: Restores shield and structural integrity.
  - 🔵 **Aegis Energy Shield**: Temporary invulnerability against direct collisions.
  - 🟣 **Tri-Laser Overdrive**: Expands standard lasers into a three-way spread-shot salvo.
  - 🟡 **Hyper-Speed Overdrive**: Boosts forward velocity, multiplier gains, and warp visuals.
- **EMP Shockwave Superweapon**:
  - Charge your overdrive meter through successful hits and evasions.
  - Unleash an expanding 3D spherical shockwave that disintegrates all threats in range.
- **Zero-Asset Procedural Audio (Web Audio API)**:
  - Custom polyphonic synth engine generating real-time laser zaps, power-up chimes, hull impact rumbles, and shockwave explosions without requiring `.mp3` or `.wav` files.

---

## 🎮 Controls

### Keyboard & Mouse

| Action | Primary Key | Alternate Key |
| :--- | :--- | :--- |
| **Move Up / Down / Left / Right** | `W` / `S` / `A` / `D` | `↑` / `↓` / `←` / `→` |
| **Primary Laser Cannons** | `Left Mouse Click` | `Spacebar` (Hold) |
| **Trigger EMP Shockwave** | `Spacebar` (Tap when 100%) | `E` |
| **Cycle Camera Angle** | `C` | UI Button |
| **Orbit / Inspect View** | `Click & Drag` | Mouse Move |
| **Audio SFX Toggle** | `M` | UI Toggle |

### Mobile & Touch Devices

- **Virtual Steering**: Touch and drag anywhere on the left or center viewport to maneuver.
- **Fire**: Tap or hold the dedicated on-screen fire trigger.
- **EMP Discharge**: Tap the glowing EMP Core button when charged.

---

## 🚀 Quick Start & Installation

Because **Cyber Horizon 3D** is entirely self-contained, no complex build tools, Node modules, or local web servers are mandatory for basic previewing.

### 1. Clone the Repository

```bash
git clone https://github.com/your-username/cyber-horizon-3d.git
cd cyber-horizon-3d
```

### 2. Launch in Browser

Simply open `index.html` in any modern web browser:

```bash
# macOS
open index.html

# Linux
xdg-open index.html

# Windows
start index.html
```

### 3. (Optional) Run via Local HTTP Server

For optimal WebGL asset caching and audio context initialization, run via a lightweight local server:

```bash
# Using Python 3
python3 -m http.server 8080

# Using Node npx
npx serve .
```

Then visit `http://localhost:8080` in your browser.

---

## 🛠️ Tech Stack & Architecture

- **Core Engine**: [Three.js](https://threejs.org/) (r128) via CDN.
- **Rendering Pipeline**:
  - `WebGLRenderer` with `PCFSoftShadowMap` and exponential depth fog (`FogExp2`).
  - Additive blending (`THREE.AdditiveBlending`) for high-luminosity neon laser beams and engine trails.
- **Audio Architecture**: Procedural Web Audio API oscillator nodes (`sine`, `sawtooth`, `triangle`) connected through dynamic `BiquadFilterNode` and `GainNode` envelopes.
- **Collision Detection**: 3D Euclidean radius-sphere bounding tests calculated in world-space every tick.
- **Styling & UI**: Tailwind CSS + custom glassmorphic styling overlays.

---

## 📂 Project Structure

```text
cyber-horizon-3d/
│
├── index.html        # Complete game source (Three.js scene, logic, HUD, & Web Audio synth)
├── README.md         # Documentation & guide
└── LICENSE           # MIT License
```

---

## 🔧 Customization & Configuration

Key game variables can be customized directly within the configuration block of `index.html`:

```javascript
const CONFIG = {
  tunnelRadius: 18,        // Radius of the cylindrical hyper-tunnel
  tunnelLength: 300,       // Visible tunnel draw distance
  baseSpeed: 42,           // Standard cruising velocity
  boostSpeed: 80,          // Velocity during Hyper-Speed Overdrive
  laserCooldown: 0.12,     // Fire rate interval (seconds)
  empChargeRate: 15,       // Overdrive energy gained per drone destroyed
};
```

---

## 🤝 Contributing

Contributions, bug reports, and suggestions are welcome!

1. Fork the Project.
2. Create your Feature Branch (`git checkout -b feature/NewHazard`).
3. Commit your Changes (`git commit -m 'Add rotating plasma grid hazard'`).
4. Push to the Branch (`git push origin feature/NewHazard`).
5. Open a Pull Request.

---

## 📄 License

Distributed under the **MIT License**. See `LICENSE` for more information.
