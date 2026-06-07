## Repository shape

Single self-contained file: [infinity-ascend-beam.html](infinity-ascend-beam.html). No build system, no package manager, no tests, no git history. Everything (HTML, CSS, JS, and a large base64-encoded JPEG background) lives inline — the file is ~350 KB because line 11 embeds the entire background image as a `data:image/png;base64,...` URL in `#bg`.

## Running it

Just open `infinity-ascend-beam.html` in a browser. The Web Audio + getUserMedia paths require a secure context — `file://` works in Chrome/Edge for local testing, but if microphone or audio playback misbehaves, serve it over `http://localhost`:

```powershell
python -m http.server 8000
# then visit http://localhost:8000/infinity-ascend-beam.html
```

There is nothing to build, lint, or test.

## What the page does

Spanish-language ("INFINITY ASCEND — Portal") full-viewport canvas visualization of a vertical light beam over a horizon, reactive to audio. Three input modes:

1. **Demo mode** (default) — `startDemo('idle' | 'medium' | 'high')` and the `#manual-slider` drive `demoTarget` directly. No audio context needed.
2. **File audio** — `onFileChange` swaps `audio-el.src`; the analyser node is wired to that `<audio>` once.
3. **Microphone** — `startMic` uses `getUserMedia` + `createMediaStreamSource`.

## Architecture (single render loop)

The whole program is one `requestAnimationFrame` loop in the `<script>` block:

```
loop(now) → updateState(dt, now) → drawFrame()
```

- **`state`** ([infinity-ascend-beam.html:216-225](infinity-ascend-beam.html#L216-L225)) holds `intensity`, `smoothedIntensity`, `bassEnergy`, `smoothedBass`, `highEnergy`, `time`, `fogOffset`, and a `particles` array (28 elements seeded at startup).
- **`getAudioMetrics`** ([infinity-ascend-beam.html:243](infinity-ascend-beam.html#L243)) reads `analyser.getByteFrequencyData` and returns `{rms, bass, high}`. Bass = FFT bins 0–12, high = bins 80–160. These hard-coded ranges assume `fftSize = 1024`.
- **`updateState`** chooses audio-driven vs. demo-driven targets, then `lerp`s state toward them with asymmetric smoothing (rises faster than it falls — see line 271-272).
- **`drawFrame`** layers, in order: sky radial → outer bloom → 4 fog layers → inner glow → core → horizon impact disc → reflected beam (flipped via `ctx.scale(1,-0.38)`) → shimmer lines → particles. The canvas uses `mix-blend-mode: screen` so it composites over the background image.

## Audio gotcha (the reason for `analyserConnected`)

`AudioContext.createMediaElementSource` can be called **only once** per `<audio>` element. The code reuses one `<audio id="audio-el">` and only wires the analyser graph on the first file load (see the `if (!analyserConnected)` guard at [infinity-ascend-beam.html:129](infinity-ascend-beam.html#L129)). When changing audio, swap `audioEl.src` — do not create a new `<audio>` element or re-call `createMediaElementSource`, or playback will fail silently in some browsers.