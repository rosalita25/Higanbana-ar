# Higanbana — The Living Bloom

A mobile-first interactive WebAR experience using the front camera, MediaPipe hand/face tracking, and a procedural Canvas renderer.

## Features

- Real camera permission flow
- Mirrored selfie preview
- Two-hand tracking
- Left thumb/index pinch controls continuous Higanbana bloom
- Right open palm releases petals
- Face tracking and a white butterfly that approaches the face
- Sudden head motion startles the butterfly
- Double blink activates a cinematic bloom moment
- Vertical PNG photo capture
- Front/back camera switch
- Local-only camera processing
- Optional debug overlay with `?debug=true`

## Run locally

Because this is a static project, no npm install is required.

```bash
python3 -m http.server 8080
```

Then open `http://localhost:8080` on desktop.

For phone testing, deploy to an HTTPS host. Camera access generally requires HTTPS outside localhost.

## GitHub Pages

1. Create a GitHub repository.
2. Upload all files from this folder.
3. Open **Settings → Pages**.
4. Choose **Deploy from a branch**.
5. Select `main` and `/root`.
6. Open the generated HTTPS URL.

## Vercel / Netlify / Cloudflare Pages

This is a static site. No build command is required. Publish the repository root.

## Privacy

All camera frames are processed locally in the browser. The project has no backend and does not upload or store face or hand data.

## Browser notes

- iPhone Safari requires a direct tap before camera permission. This project does that.
- The page uses `playsinline` for iPhone.
- MediaPipe models load from Google-hosted model URLs and the MediaPipe package loads from jsDelivr, so internet access is required when the experience starts.
- Composed video recording is deliberately not enabled because browser support, especially on Safari, is inconsistent. Photo capture is implemented.

## Debug mode

Append `?debug=true` to the URL to show FPS, bloom progress, and butterfly state.
