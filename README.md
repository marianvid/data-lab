# Data-Lab

> **Personal use.** This repository is not a product, a hosted service or a
> complete distribution of Data-Lab. It has no support commitment.

Data-Lab prepares data for my local projects. Most of it is private because its
workflows may contain confidential source material, source inventories and
operational details.

## Why this repository is public

The public surface has one purpose: to show exactly how the Romanian audio used
in my [AI-Lab](https://github.com/marianvid/ai-lab) evaluations was prepared.
It contains the script that ran on Data-Lab, the dataset provenance and the
normalisation procedure. This makes the audio measurements reproducible without
publishing the downloaded corpus or any personal data.

The current method takes the official FLEURS `ro_ro` test split, selects rows at
equal intervals over the complete table, and uses FFmpeg to create mono, 16 kHz,
signed 16-bit PCM WAV files. See [the audio preparation method](audio/README.md).

## What is private

The rest of Data-Lab is kept in a separate private repository named
`data-lab-opts`, checked out locally as `opts/`. It includes the broader data
service, operational configuration, private source handling and workflows that
may reveal confidential data. `opts/` is not a submodule and is deliberately
excluded from this repository.

No audio, parquet files, generated manifests, downloaded corpora, databases or
credentials belong in this public repository.

## Licence

MIT. The source dataset retains its own licence; FLEURS is CC BY 4.0.
