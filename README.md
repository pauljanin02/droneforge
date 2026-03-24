DroneForge 3D (made with Claude)
A browser-based toolkit for drone photographers who want to prepare photogrammetry sessions and visualize the resulting 3D models — no installation required, no server, no data ever leaves your computer.
---
What's included
File	Description
`drone3d.html`	Photo manager — upload, organize and export images ready for Meshroom
`viewer3d.html`	3D viewer — load and explore `.obj` models, generate shareable reports
---
Workflow
```
Drone photos  →  drone3d.html  →  Meshroom (local)  →  viewer3d.html
   (upload)       (organize)       (3D reconstruction)    (view + report)
```
Step 1 — Organize your photos (`drone3d.html`)
Open `drone3d.html` in any modern browser
Drag and drop your drone photos (JPG, PNG, DNG, TIFF, HEIC — up to 200+ images)
Configure the project: subject type, quality preset, output format
Check the coverage analysis to make sure you have enough images
Export a ZIP package containing all images + a `meshroom_project.json` config file
Step 2 — Reconstruct in Meshroom
Download Meshroom (AliceVision) — free and open source
Extract the ZIP exported in Step 1
Open Meshroom and drag the `images/` folder into the workspace
Click Start — processing takes 30–120 minutes depending on your hardware
Find the finished model in `MeshroomCache/Texturing/`
> **Tip:** An NVIDIA GPU dramatically speeds up processing. Meshroom uses CUDA for the feature matching pipeline.
Step 3 — View and share (`viewer3d.html`)
Open `viewer3d.html` in any modern browser
Drag your `.obj` file into the sidebar (optionally add `.mtl` and a texture image)
Explore the model: orbit, zoom, wireframe, lighting controls, preset views
Fill in the project details in the Report tab
Click Generate report to produce a standalone HTML page with a screenshot, model stats, and all your notes — ready to share with anyone
---
Photo capture tips
Good photogrammetry starts in the air. Follow these guidelines for the best results:
Overlap: shoot with at least 70–80% overlap between consecutive frames
Orbit passes: fly a full 360° orbit around the subject at multiple altitudes
Oblique angles: include 45° angled shots alongside nadir (straight-down) passes — essential for capturing roofs, facades, and corners of buildings
Consistent altitude: keep a steady flight height during each pass
Diffuse light: overcast days work best; avoid harsh shadows and backlit conditions
Minimum count: 30 images is the bare minimum; 100–200 gives reliable results; 200–300 is recommended for complex subjects like castles or ruins
---
System requirements
drone3d.html and viewer3d.html
Any modern browser (Chrome, Firefox, Safari, Edge)
No internet connection required after the first load (fonts are loaded from Google Fonts)
No installation, no backend, no account
Meshroom
Windows 10/11 or Linux (macOS not officially supported)
NVIDIA GPU with CUDA support strongly recommended
16 GB RAM minimum; 32 GB recommended for large datasets
10–50 GB free disk space depending on model complexity
---
Supported file formats
Format	Support
JPG / JPEG	✅ Upload + 3D texture
PNG	✅ Upload + 3D texture
DNG / RAW	✅ Upload (browser preview may vary)
TIFF	✅ Upload
HEIC	✅ Upload
OBJ	✅ 3D viewer
MTL	✅ Material loading
GLB / FBX / PLY	Export config only (processed by Meshroom)
---
Hosting
Both files are self-contained single-page applications. Host them anywhere that serves static HTML:
Altervista — upload to `htdocs/` via File Manager or FTP
Netlify — drag and drop the files at netlify.com for an instant public URL
GitHub Pages — push to a repository and enable Pages in settings
Locally — just open the `.html` files directly in your browser
---
Privacy
All processing happens entirely in your browser. No photos, models, or project data are ever uploaded to any server. The only external requests are font files loaded from Google Fonts on first use.
---
Built with
Three.js r128 — 3D rendering engine
JSZip 3.10 — ZIP package export
Meshroom / AliceVision — photogrammetry pipeline (separate download)
---
License
Free to use and modify for personal and commercial projects.
---
Made for drone photographers who love castles, buildings, and landscapes — and want to turn their flights into 3D models.
