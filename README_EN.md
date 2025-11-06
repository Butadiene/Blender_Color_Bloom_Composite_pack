# Color Bloom Composite Pack

A **Blender compositing template / asset pack** that ships with four node groups.  
Just drag & drop from the Asset Browser to finish your stills and clips.

- **Vignette** — Subtle edge darkening. Control radius and blur softness.  
- **Color Bloom** — Adds highlight bloom and color tinting to create mood.  
- **Bloom** — Simple highlight extraction + diffusion + mixing.  
- **Overlay_Color_Grading** — One‑stop color/brightness control via Overlay blend.

---

## Package Layout

```
Color_Bloom_Composite_pack/
  demo/
    after_composite.mkv
    before_composite.mkv
    compare.mkv
  Color_Bloom_Composite_Library/
    composite_example.blend
    composite_example.blend1
  README.md
  README_EN.md
  SIMPLE_TUTORIAL_JA.md
  SIMPLE_TUTORIAL_EN.md
  LICENSE.txt
  CHANGELOG.md
```

> **Licensing**  
> - Assets under `Color_Bloom_Composite_Library/` are **CC0** (public‑domain equivalent).  
> - Media under `demo/` is **CC BY 4.0** (attribution required).  
> See `LICENSE.txt` for details.

---

## Requirements

- **Blender**: tested with **4.5 LTS**  
- No extra add‑ons (built‑in nodes only)

---

## Installation (as an Asset Library)

1. Open `Edit > Preferences > File Paths > Asset Libraries`.  
2. Click **Add** and select `Color_Bloom_Composite_pack/Color_Bloom_Composite_Library`.  
3. Open the Asset Browser, choose the catalog you added (under **Catalogs**), then drag & drop the assets.

> To append directly from the `.blend`:  
> `File > Append` → `composite_example.blend` → `NodeTree/` → choose **Vignette**, **Color Bloom**, **Bloom**, **Overlay_Color_Grading**.

---

## Quick Start

1. In the **Compositor**, enable **Use Nodes** and connect a **Viewer** node.  
2. Chain assets in this order (recommended):  
   `Exposure (opt.) → Color Bloom → Vignette → Overlay_Color_Grading → (Brightness/Contrast) → Composite`  
   For inputs, use an **Image** node (still) or a **Movie Clip** node (video) and connect it to the chain head.  
3. See `Color_Bloom_Composite_Library/composite_example.blend` for a ready‑to‑try setup.

### Key Parameters
> Socket names/order in UI may differ slightly by version; treat these as guides.

- **Color Bloom**  
  - **Image** — Source image  
  - **Value (Blur Size)** — Diffusion amount  
  - **Factor (Bloom Mix)** — Bloom intensity (Lighten blend)  
  - **Image (Shadow Tint)** — Tint color for darker areas  
  - **Image (Highlight Tint)** — Tint color for highlights (white or light colors recommended)  
  - **Value (Recolor Strength)** — Strength of recolor image  
  - **Factor (Recolor Overlay)** — Overlay amount of recolor onto the base  

- **Vignette**  
  - **Image** — Source image  
  - **Image (Vignette Color)** — Vignette color  
  - **Factor** — Intensity (0–1)  
  - **Size (Blur)** — Edge softness  
  - **Size (Radius)** — Vignette radius  

- **Bloom (utility)**  
  - **Image** — Source image  
  - **Value (Blur Size)** — Diffusion amount  
  - **Factor** — Bloom mix amount  

- **Overlay_Color_Grading (utility)**  
  - **A (Base Image)** — Base image  
  - **Vector (Tint Color)** — Tint color  
  - **Value (Strength)** — Tint strength  
  - **Factor (Overlay Mix)** — Overlay blend amount  

4. Send the final image to the **Composite** node; preview via **Viewer**.

---

## Sample Files

- `Color_Bloom_Composite_Library/composite_example.blend` contains a combined setup of the four assets.  
- **Before / After / Compare** videos are under `demo/` (CC BY 4.0).

---

## FAQ

- **I see “Missing Files”.**  
  Use `File > External Data > Report Missing Files` and, if needed, `Make All Paths Relative`.

- **Commercial use?**  
  Yes. Assets under `Color_Bloom_Composite_Library/` are CC0 (free to use/redistribute). Demo media under `demo/` is CC BY 4.0 and requires attribution.

---

## Credits / Contact

- **LinkAster**  
- Contact: linkaster71@gmail.com

---

## Changelog
See `CHANGELOG.md`.
