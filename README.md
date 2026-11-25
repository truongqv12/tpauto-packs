# tpauto-packs

This repository holds only third-party models and libraries that tpauto downloads at run time.
It contains no tpauto code.

Each release asset is a pack zip with:

- `pack-manifest.json`: the path, size and sha256 of every file in the pack;
- `SBOM.json`: each file's upstream, revision and licence;
- `NOTICES` and `LICENSES/`: the attribution and licence texts of every component.

`packs-sbom.json` covers the whole release. The FFmpeg build in `dub-runtime` is the BtbN LGPL
shared build; `ffmpeg-lgpl-source-1.tar.gz` is its complete corresponding source (FFmpeg, the build
scripts and every LGPL or MPL library it links), kept for as long as the pack is offered.

tpauto trusts a pack only when its sha256 matches the value pinned in the tpauto binary; the URL is
not a source of trust.