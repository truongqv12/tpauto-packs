# tpauto-packs

This repository holds only third-party models and libraries that tpauto downloads at run time.
It contains no tpauto code.

Each pack zip of a release holds the pack's files and `pack-manifest.json`: the path, size and
sha256 of every file in the pack. tpauto trusts a pack only when the zip's sha256 matches the value
pinned in the tpauto binary, checks every unpacked file against the manifest, and refuses a pack
folder that holds a file its manifest does not list. The URL is not a source of trust.

Packs of release `packs-v2`:

- `dub-runtime-<n>.zip`: ONNX Runtime, sherpa-onnx, the Microsoft Visual C++ runtime and ffmpeg
  (from version 3, the BtbN GPL shared build of FFmpeg 8.1, with libx264, NVENC, libass, delogo and
  boxblur; see https://github.com/BtbN/FFmpeg-Builds, release `autobuild-2026-11-24-12-41`).
- `dub-models-<n>.zip`: the OCR, voice-activity and speech-recognition models and the subtitle font.
- `voice-models-<n>.zip`: the VieNeu-TTS and MOSS audio tokenizer models and the preview samples.
- `voice-deps-<version>.zip`: the Python packages of the voice tool's engine, as their wheels install.

`vieneu-previews-<n>.zip` holds the preview samples of `voice-models` (`previews/vieneu/<voice>.wav`)
as generated: each VieNeu-TTS preset voice speaking one fixed sentence. No upstream publishes them,
so the release keeps them; tpauto never downloads this asset.
