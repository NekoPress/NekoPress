# NekoPress

Quality-first image compression engine for Windows (portable).

## Download

Use the latest release page:
- https://github.com/NekoPress/NekoPress/releases/latest

Download:
- `NekoPress <version>.exe`
- `SHA256SUMS.txt` (optional integrity check)

## How to use

1. Run `NekoPress <version>.exe`
2. Add JPG or PNG files (one format per run)
3. Choose output folder
4. Select quality mode
5. Start conversion

## Notes

- Portable app (no installer)
- Windows SmartScreen warning may appear on unsigned builds
- For support, use the GitHub repository issues page

## Security

- Electron hardening enabled: `contextIsolation: true`, `sandbox: true`, `nodeIntegration: false`.
- External link policy is restricted to the official repository URL only.
- Support logs are local-only and masked (path/username tokens are hashed before write).
- Release assets include `SHA256SUMS.txt` for integrity verification.

## Reliability

- Cancel policy: the current in-flight file finishes safely, then remaining files are skipped.
- Output writing uses atomic flow (`temp -> rename`) to reduce partial/corrupt output risk.
- Preferences are normalized/migrated across schema updates.
- Runtime compatibility guard blocks start on IPC contract mismatch.

## Quality and Performance

- Quality-first pipeline with three presets: `High Detail`, `Balanced`, `Small Display`.
- Conversion is tuned for visual quality retention with practical size reduction.
- Automated gates are used before release (quality, privacy, update compatibility, stage checks).
- Throughput depends on CPU/storage/input complexity; policy prioritizes quality and stability over raw speed.

## System Requirements

- OS: Windows 10/11 (x64)
- Architecture: x64
- RAM: 8 GB minimum (16 GB recommended for large batches)
- Storage: SSD recommended
- Distribution: Portable executable (no installer required)
