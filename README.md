# TTS alignment test app

Simple tool to generate TTS with timestamps, play the audio, and verify alignment by clicking words or jumping to a time.

## Run

All client-side JS. Just open `index.html` in a browser and it will work. Deploy as you like.

## Use

1. **Generate** – Enter text, voice ID, and API key. Optionally set API base, model ID, and output format. Click **Generate**. The app calls `POST /v1/text-to-speech/{voice_id}/with-timestamps` and shows the audio plus word-level timestamps.
2. **Load existing** – Paste JSON with `audio_base64` and `alignment` (with `characters`, `character_start_times_seconds`, `character_end_times_seconds` or `_ms`). Click **Load** to use that audio and alignment instead of generating.
3. **Playback** – Use the audio controls, **Go to time (s)** to seek and play from a given second, or **click any word** to seek to its start time and play. Use this to check whether the reported timestamps match what you hear.

Alignment is shown at **word level** (derived from character alignment). Supports both `character_*_times_seconds` and `character_*_times_ms`.
