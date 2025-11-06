# First Steps: Swap Your Source and Render (Super Simple)
Audience: Blender beginners (photo/video) • Time: **5–10 min**  
File used: `Color_Bloom_Composite_Library/composite_example.blend` (compositor nodes already connected)

---

## Goal
- Open the included `.blend`
- Replace the input with your own image **or** video
- Tweak just a couple of parameters to see the look
- Render to a still or a video

---

## 1) Open the `.blend`
1. Launch Blender → **File > Open** → open `Color_Bloom_Composite_Library/composite_example.blend`.
2. Switch to **Compositing** and make sure **Use Nodes** is enabled.  
   - This scene contains **no 3D objects**—only a **pre‑wired compositor node chain**.

---

## 2) Swap your source (image or video)
### For an image
1. In the node editor: **Shift+A > Input > Image** → **Open** your photo.
2. Replace the existing Movie clip input and connect it at the **start** of the chain (keep the rest as is).

### For a video
1. **Shift+A > Input > Movie Clip** → **Open** your clip.
2. Connect Movie Clip at the **start** of the chain.
3. In **Output Properties > Frame Range**, set **Start/End** to your clip length.

> For live preview, add **Shift+A > Output > Viewer** and connect the end of the chain to the Viewer output.

---

## 3) Make tiny tweaks
- Adjust just **one** obvious control (e.g., *Factor*, or *Color*) slightly to feel the effect.  
- Use **Ctrl+Z** to compare before/after as you experiment.  
- Parameter descriptions are in README_EN.md.


---

## 4) Render
### Still image
1. Press **F12** to render.
2. **Image > Save** to save your result (common formats: **PNG** or **JPEG**).

### Video
1. In **Output Properties**:  
   - **File Format** → `FFmpeg video`  
   - **Container** → `MPEG-4`  
   - **Video Codec** → `H.264`
2. Set your output path (folder icon in **Output**).
3. **Render > Render Animation** to export.

---

## FAQ
- **All black/white output**: ensure your input node is connected at the chain start; also connect the end to **Viewer** for checking.  
- **Clip too short/long**: adjust **Start/End** under **Output Properties > Frame Range**.  

