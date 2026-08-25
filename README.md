# Data-Lab

> **Personal use.** This repository is not a product, a hosted service or a
> complete distribution of Data-Lab. It has no support commitment.

Data-Lab prepares audio data for my personal AI-Lab evaluations.

## Why this repository is public

The public surface has one purpose: to show exactly how the Romanian audio used
in my [AI-Lab](https://github.com/marianvid/ai-lab) evaluations was prepared.
It contains the script that ran on Data-Lab, the dataset provenance and the
normalisation procedure. This makes the audio measurements reproducible without
publishing the downloaded corpus or any personal data.

The current method takes the official FLEURS `ro_ro` test split, selects rows at
equal intervals over the complete table, and uses FFmpeg to create mono, 16 kHz,
signed 16-bit PCM WAV files. See [the audio preparation method](audio/README.md).

## Licence

MIT. The source dataset retains its own licence; FLEURS is CC BY 4.0.
