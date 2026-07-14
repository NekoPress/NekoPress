# NekoPress

Quality-first image compression engine for Windows (portable).

## Download

Use the latest release page:

- https://github.com/NekoPress/NekoPress/releases/latest

Files:

- `NekoPress-1.1.5.exe`
- `SHA256SUMS.txt` (optional integrity check)

## How to use

1. Run `NekoPress-1.1.5.exe`
2. Add **JPG or PNG** files (**one format per run**)
3. Choose output folder
4. Select quality mode (`High Detail` / `Balanced` / `Small Display`)
5. Start conversion

## Security

- Electron hardening enabled (`contextIsolation: true`, `sandbox: true`, `nodeIntegration: false`)
- External link policy is restricted to the official repository URL
- Support logs are local-only and path-masked
- Release integrity file included (`SHA256SUMS.txt`)

## Reliability

- Cancel policy: current in-flight file finishes safely, then remaining files are skipped
- Atomic output flow (`temp -> rename`) to reduce partial/corrupt output risk
- Preferences normalization/migration is built in
- Runtime compatibility guard is enabled (IPC contract check)

## Quality and performance

- Quality-first pipeline with three presets
- External golden-set based release quality gate
- Release checks include version governance, privacy, quality, compatibility, and artifact scan
- Throughput depends on CPU/storage/input complexity; quality and stability are prioritized over raw speed

## System requirements

- OS: Windows 10/11 (x64)
- RAM: 8 GB minimum (16 GB recommended for large batches)
- Storage: SSD recommended
- Distribution: portable executable (no installer)

## Input Support and Output Guarantees

- Input support: standard non-animated JPG/JPEG and single-frame PNG. Some CMYK/profiled JPG and 16-bit PNG inputs may also open when the current decoder can read them.
- Output guarantees: re-encoded outputs are generated for practical web-upload use. They strip EXIF/XMP/IPTC/ICC by default. Same-format copied fallback also removes copied metadata and keeps only a minimal orientation tag when that is required for display correctness. ICC/profile retention and 16-bit PNG output preservation are not guaranteed in the current release line.
- Keep original files if exact metadata, ICC/profile retention, or bit-depth preservation matters.

## Notes

- Windows SmartScreen warning may appear on unsigned builds
- AVIF can be slow on low-spec CPUs with very large images (quality-first policy)

## Optional integrity check

```powershell
Get-FileHash ".\NekoPress-1.1.5.exe" -Algorithm SHA256
```
