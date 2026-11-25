# TennisLab

A browser-based motion-controlled tennis practice game from OpenSportSense.

## [Play TennisLab](https://aaron-ragsdale.github.io/TennisLab/)

### Getting started
1. Open the game in a browser with WebGL and webcam support.
2. Clear enough space around you to swing safely. No physical racket is needed.
3. Select your dominant hand and enable the camera.
4. Test your swing while standing with your shoulders, hips and arm visible.
5. Start practice and swing when prompted.

| Swing | Shot |
|---|---|
| Low to high | Topspin |
| High to low | Slice |
| Across your body | Flat |

Keyboard testing: Q = slice, W = flat, E = topspin during the contact window. Adjust smoothing, sensitivity and feed speed in the sidebar. Export session metrics as CSV.

### How it works
MediaPipe Pose Landmarker estimates body landmarks locally. A rolling wrist trajectory relative to the shoulders estimates swing angle and speed. Three.js renders the court, racket and simulated ball trajectories. The initial classifier uses heuristic thresholds; it does not measure true racket-face orientation, physical ball spin or real-world swing speed. Contact is currently timing-based, not a full racket-ball collision simulation.

### Privacy
Camera frames are processed in the browser. The app does not upload or record video. Libraries and model weights are loaded from external CDNs/model hosting on initialization. No API key or backend is required.

### Hosting
In the repository, open Settings > Pages, choose Deploy from a branch, select main and / (root), then Save.

### Roadmap
- Tune swing detection and contact timing with real player tests.
- Add spatial contact, directional control and more realistic spin physics.
- Add shot challenges and a computer-controlled opponent.
