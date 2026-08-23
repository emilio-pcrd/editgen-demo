# EditGen — Controllable Autoregressive Music Editing

Companion website (audio samples) for the EditGen internship project.

- **Page:** a single self-contained `index.html` — no build step, no framework.
- **Live:** https://emilio-pcrd.github.io/editgen-demo/

## Adding audio

Drop the clips into `audio/<section>/`, keeping the filenames in sync with the `<audio src="...">`
entries in `index.html`. Empty players are intentional placeholders until the clips land.

```
audio/generation/    ex1_gen.mp3   ex2_gen.mp3
audio/continuation/  ex1_cont.wav  ex2_cont.wav  ex3_cont.wav  ex4_cont.wav   (single clip: first 2.5 s = context, rest generated)
audio/text2music/    ex1_gen.mp3  ex2_gen.mp3  ex3_gen.wav  ex4_gen.mp3  ex5_gen.wav  ex6_gen.wav   (+ texts.txt holds the prompts)
audio/melody/        ex1_melody.mp3  ex1_ours.mp3   ex2_melody.mp3  ex2_ours.mp3
audio/infilling/     ex1_melody.wav  ex1_truth.wav  ex1_ours.wav    (ex1 = melody-conditioned)
                     ex2_truth.wav   ex2_ours.wav                   (ex2 = text-conditioned)
                     ex3_truth.wav   ex3_ours.wav                   (ex3 = unconditioned)
audio/schaeffer/     prompt/ex1_ref.wav        prompt/ex1_ours.wav        (text prompt + training reference)
                     prompt/ex2_ref.wav        prompt/ex2_ours.wav
                     continuation/ex1_ref.wav  continuation/ex1_ours.wav  (continuation + training reference)
audio/stems/         bass_original.mp3    bass_stem.mp3    bass_newmix.mp3
                     melody_melody.mp3    melody_original.mp3
                     melody_stem.mp3      melody_newmix.mp3
                     voice_original.mp3   voice_stem.mp3   voice_newmix.mp3

PICARD_Emilio_Memoire_Stage.pdf   internship report, linked from the page header
```

The conditioning text/melody labels in `index.html` are placeholder copy — edit them to match the
actual clips. Rows are self-contained, so add or remove them freely.

## Local preview

Just open `index.html` in a browser (paths are relative), or serve the folder:
`python3 -m http.server`.
