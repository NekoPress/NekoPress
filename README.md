# NekoPress

Quality-first image compression engine for Windows (portable).

## Download

Use the latest release page:

- https://github.com/NekoPress/NekoPress/releases/latest

Files:

- `NekoPress 1.1.1.exe`
- `SHA256SUMS.txt` (optional integrity check)

## How to use

1. Run `NekoPress 1.1.1.exe`
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

## Notes

- Windows SmartScreen warning may appear on unsigned builds
- AVIF can be slow on low-spec CPUs with very large images (quality-first policy)

## Optional integrity check

```powershell
Get-FileHash ".\NekoPress 1.1.1.exe" -Algorithm SHA256
