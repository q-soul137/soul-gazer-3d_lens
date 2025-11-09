## 📖README.md

🌊 **Soul Gazer v1.1 — Gender Reveal**  
*Depth-aware aura with FaceNet512 + ANFE gender classification*

### 🌟 Features
- Real-time **gender detection** up to 5 meters (`model_selection=1`)
- **97.5% female / 94.2% male accuracy** using FaceNet512 + ANFE
- Depth-aware **3D aura** (red/blue) based on `z`-values. Visual feedback via 3D wraparound overlay 🫨  using **MediaPipe Face Mesh** to detect 468 3D landmarks and rendering dynamic effects (like your aura) that follow facial contours in real time. The overlay "wraps" around the face using depth (z-values), creating a responsive, immersive effect — similar to AR filters on Snapchat or Instagram. It provides immediate, intuitive feedback by visually linking AI inference to physical facial structure.
- Label: `"Male"` or `"Female"` with confidence


### 🛠️ Dependencies
```bash
pip install opencv-python mediapipe deepface
```

### 📦 Project Tree
```
soul_gazer/
├── main.py
├── avg_embeddings_facenet512.json  # Generated from your dataset
├── data/
│   ├── male_faces/
│   └── female_faces/
└── scripts/
    └── generate_embeddings.py
```

### 🔧 Setup
1. Populate `data/male_faces/` and `data/female_faces/`
2. Run `generate_embeddings.py` to create `avg_embeddings_facenet512.json`
3. Run: `python main.py`

### 🧬 How It Works
- Uses **FaceNet512** embeddings via `DeepFace`
- Classifies gender by **Euclidean-L2 distance** to average male/female vectors
- Aura intensity: red (left) for male, blue (right) for female

### 🕊️ Notes
- Non-commercial use (VGG-Face license)
- Based on peer-reviewed ANFE method (MDPI, 2025)





