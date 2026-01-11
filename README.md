<div align="center">

# 🚀 Space Station WebGL Viewer

### *Blender → WebGL Pipeline using Three.js*

[![Three.js](https://img.shields.io/badge/Three.js-v0.160.0-black?style=for-the-badge&logo=three.js&logoColor=white)](https://threejs.org/)
[![WebGL](https://img.shields.io/badge/WebGL-2.0-990000?style=for-the-badge&logo=webgl&logoColor=white)](https://www.khronos.org/webgl/)
[![HTML5](https://img.shields.io/badge/HTML5-E34F26?style=for-the-badge&logo=html5&logoColor=white)](https://developer.mozilla.org/en-US/docs/Web/HTML)
[![JavaScript](https://img.shields.io/badge/JavaScript-ES6+-F7DF1E?style=for-the-badge&logo=javascript&logoColor=black)](https://developer.mozilla.org/en-US/docs/Web/JavaScript)

<br/>

*Transform stunning 3D models into immersive, browser-based WebGL experiences*

<img src="https://media.giphy.com/media/l0HlNQ03J5JxX6lva/giphy.gif" width="500px" alt="Space Animation"/>

---

</div>

## 🌌 Overview

An interactive **3D Space Station Viewer** built with cutting-edge web technologies.  This project demonstrates the complete pipeline of taking a Blender-compatible 3D model and rendering it beautifully in the browser using **Three.js** — complete with cinematic lighting, post-processing bloom effects, and smooth orbital controls.

> *"Any sufficiently advanced technology is indistinguishable from magic."* — Arthur C. Clarke

---

## ✨ Features

| Feature | Description |
|---------|-------------|
| 🎨 **ACES Filmic Tone Mapping** | Cinema-grade color grading for realistic visuals |
| 💫 **Unreal Bloom Pass** | Real-time bloom post-processing for glowing lights |
| 🔄 **Orbit Controls** | Smooth damped rotation with auto-rotate functionality |
| 📱 **Responsive Design** | Adapts seamlessly to any screen size |
| ⚡ **High Performance** | Optimized rendering with pixel ratio capping |
| 🌟 **PBR Materials** | Physically-based rendering with environment mapping |
| 🔵 **Dynamic Lighting** | Dual directional lights with ambient blue accent |
| 🎭 **Custom Loading Screen** | Elegant spinner animation during model load |

---

## 🛠️ Tech Stack

```
┌─────────────────────────────────────────────────────────┐
│                    RENDERING ENGINE                     │
├─────────────────────────────────────────────────────────┤
│  Three.js v0.160.0                                      │
│  ├── GLTFLoader      → 3D Model Import (. glb/. gltf)   │
│  ├── OrbitControls   → Interactive Camera Movement      │
│  ├── RoomEnvironment → HDR Environment Mapping          │
│  └── PostProcessing  → Bloom, Render, Output Passes     │
└─────────────────────────────────────────────────────────┘
```

---

## 🎮 Live Demo

Simply open `index.html` in any modern browser — no build step required! 

```bash
# Clone the repository
git clone https://github.com/Siddharthk17/Blender-To-Webgl-Using-Three-JS.git

# Navigate to project
cd Blender-To-Webgl-Using-Three-JS

# Open in browser (or use a local server)
# Option 1: Direct file
open index.html

# Option 2: Python server (recommended)
python -m http.server 8000
# Then visit http://localhost:8000

# Option 3: VS Code Live Server
# Right-click index.html → "Open with Live Server"
```

---

## 📐 Architecture

```
Blender-To-Webgl-Using-Three-JS/
│
├── 📄 index.html          # Single-file application
│   ├── 🎨 Styles          # Inline CSS (loader, canvas)
│   ├── 📦 Import Map      # CDN-based Three.js modules
│   └── 🚀 SpaceStationViewer Class
│       ├── init()         # Scene, Camera, Renderer setup
│       ├── loadModel()    # GLTF loading & material processing
│       ├── onResize()     # Responsive handler
│       └── animate()      # Render loop
│
└── 🛸 space_station.glb   # 3D Model Asset
```

---

## 🎯 Key Implementation Details

### 🔮 Post-Processing Pipeline

```javascript
// Cinematic bloom configuration
const bloomPass = new UnrealBloomPass(
    new THREE.Vector2(window.innerWidth, window.innerHeight),
    1.5,   // strength  → Intensity of the glow
    0.4,   // radius    → Spread of the bloom
    0.75   // threshold → Brightness cutoff
);
```

### 🔵 Intelligent Material Processing

The viewer automatically detects and enhances emissive materials:

```javascript
// Auto-detect blue lights and enhance glow
if (isBlueColor || isBlueName) {
    m.emissiveIntensity = 10.0;  // High intensity for bloom
    m.toneMapped = false;         // Bypass tone mapping
}
```

### 📷 Camera & Controls

```javascript
// Smooth orbital controls with auto-rotation
this.controls. enableDamping = true;
this.controls.autoRotate = true;
this.controls.autoRotateSpeed = 0.5;
```

---

## 🎨 3D Model Attribution

<div align="center">

| | |
|---|---|
| **Model** | [Space Station](https://sketchfab.com/3d-models/space-station-0da4a24e7edd49159737675ffcc06228) |
| **Platform** | Sketchfab |
| **Format** | GLB (Binary GLTF) |

</div>

---

## 🚀 Use Your Own Model

Want to display your own 3D creation? It's simple:

1. **Export from Blender** as `.glb` or `.gltf`
2. **Place** your model file in the project root
3. **Update** the loader path in `index.html`:

```javascript
loader.load('your_model.glb', (gltf) => {
    // ... 
});
```

---

## 🌐 Browser Support

| Browser | Status |
|---------|--------|
| Chrome 80+ | ✅ Fully Supported |
| Firefox 75+ | ✅ Fully Supported |
| Safari 14+ | ✅ Fully Supported |
| Edge 80+ | ✅ Fully Supported |

> **Note:** WebGL 2.0 support required

---

## 📚 Learning Resources

- 📖 [Three.js Documentation](https://threejs.org/docs/)
- 🎓 [Three.js Fundamentals](https://threejs.org/manual/#en/fundamentals)
- 🎨 [Blender to Web Guide](https://threejs.org/docs/#manual/en/introduction/Loading-3D-models)
- ✨ [Post-Processing in Three.js](https://threejs.org/docs/#manual/en/introduction/How-to-use-post-processing)

---

## 🤝 Contributing

Contributions are welcome! Feel free to: 

- 🐛 Report bugs
- 💡 Suggest features
- 🔧 Submit pull requests

---

## 📄 License

This project is open source and available under the [MIT License](LICENSE).

---

<div align="center">

### Built with 💙 and Three.js

**[⬆ Back to Top](#-space-station-webgl-viewer)**

<br/>

*If you found this project interesting, consider giving it a ⭐*

</div>
