# Romanian audio preparation

This is the preparation step used before sending Romanian audio to
[AI-Lab](https://github.com/marianvid/ai-lab). It prepares data only; model
loading, inference and scoring are outside this repository.

## Source and selection

The source is the official `ro_ro` test split of
[FLEURS](https://huggingface.co/datasets/google/fleurs), licensed CC BY 4.0.
The converted parquet is downloaded directly from its publisher. No source
audio or reference transcript is redistributed here.

For a limit of 100, row `i` is selected as:

```text
floor(i × total_rows / 100), for i = 0..99
```

This covers the whole official test ordering and prevents selecting examples
after seeing model output.

## Normalisation

Every selected encoded file is passed through FFmpeg and written as:

- one channel;
- 16,000 Hz;
- signed 16-bit PCM WAV.

The script writes `MANIFEST.json` beside the generated audio. It records the
dataset, source URL, licence, selected source rows, identifiers, durations and
reference transcripts. Both the manifest and generated audio are ignored by
Git.

## Reproduce it

The recorded run used Python 3.13, PyArrow 25.0.1 and FFmpeg/FFprobe 7.1.5.
Other recent versions should produce the same selection and audio format.

```sh
python3 -m venv .venv
.venv/bin/pip install -r requirements.txt

curl -L \
  'https://huggingface.co/datasets/google/fleurs/resolve/refs%2Fconvert%2Fparquet/ro_ro/test/0000.parquet' \
  -o fleurs-ro-test.parquet

.venv/bin/python audio/prepare_fleurs.py fleurs-ro-test.parquet \
  --out prepared/fleurs-ro \
  --limit 100
```

FFmpeg and FFprobe must be available on `PATH`. The generated files remain
local and must not be committed.
