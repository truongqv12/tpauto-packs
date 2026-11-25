# tpauto-packs

This repository holds only third-party models and libraries that tpauto downloads at run time.
It contains no tpauto code.

Each pack zip of a release holds:

- `pack-manifest.json`: the path, size and sha256 of every file in the pack;
- `SBOM.json`: each file's upstream, revision and licence, and the libraries compiled into it;
- `NOTICES` and `LICENSES/`: the attribution and licence texts of every component.

`packs-sbom.json` covers the whole release.

Source assets (tpauto never downloads them; they are kept for as long as the packs are offered):

- `ffmpeg-lgpl-source-2-<n>.tar.gz`: the complete corresponding source of the FFmpeg build in
  `dub-runtime` (the BtbN LGPL shared build): FFmpeg, the build scripts and every library the build
  links into the DLLs, with the submodules it compiles, the Rust crates of librsvg and rav1e and the
  files it downloads. It is split into parts at library boundaries to stay under GitHub's limit for
  one asset; `SOURCES.txt` at the end of each part lists every library and says which that part holds.
- `eigen-<commit>.zip` and `eigen-5.0.1.tar.gz`: the Eigen (MPL-2.0) that ONNX Runtime and
  sherpa-onnx compile in, as upstream publishes it.
- `vieneu-previews-<n>.zip`: the preview samples of `voice-models` (`previews/vieneu/<voice>.wav`), as
  generated: each VieNeu-TTS preset voice speaking one fixed sentence. They are output of VieNeu-TTS
  (Apache-2.0); no upstream publishes them, so the release keeps them.

tpauto trusts a pack only when its sha256 matches the value pinned in the tpauto binary; the URL is
not a source of trust.
