# Acoustic Reel Studio

Browser-based 9:16 reel editor for solo acoustic performances. Everything runs client-side: no backend, no API keys, no special headers. It is a single `index.html` (Tailwind and Google Fonts load from CDN), so there is no build step.

## Deploy to GitHub Pages

1. Create a new GitHub repository (e.g. `acoustic-reel-studio`).
2. Put `index.html` and `README.md` at the **root** of the repo:
   ```bash
   git init
   git add index.html README.md
   git commit -m "Acoustic Reel Studio"
   git branch -M main
   git remote add origin https://github.com/<you>/acoustic-reel-studio.git
   git push -u origin main
   ```
3. On GitHub: **Settings → Pages → Build and deployment**. Set **Source** to *Deploy from a branch*, **Branch** to `main`, folder `/ (root)`. Save.
4. After about a minute the app is live at `https://<you>.github.io/acoustic-reel-studio/`.

To use it locally, just open `index.html` in Chrome, Edge or Firefox.

## Workflow

1. **Clip & Trim:** drop your video, then pick a preset or drag the two handles.
2. **Smart Cuts:** choose a pace, then drag the Wide / Face / Guitar frames on the source view to aim them. Adjust punch-in, Ken Burns drift and Strum Pulse.
3. **Chaleur & Grade:** pick a look, then fine-tune.
4. **Lyrics & Export:** paste lyrics, press *Start Tap Sync* and tap Space on each line. Then choose a font and click *Render & Download*.

## Notes

- Export records in **real time** through `MediaRecorder`. Keep the tab in the foreground while it renders.
- Output is MP4 (H.264/AAC) where the browser supports it (recent Chrome/Edge, Safari). Otherwise it falls back to WebM.
- Contrast and saturation use canvas filters, which Safari ignores. Warmth, vignette, grain and lyrics bake into the export everywhere.
- **Style DNA** (`style-dna.json`) stores grade, pacing, zoom, shot framing and lyric typography. Import it on any future clip to keep the same look.
- Videos never leave your device.
