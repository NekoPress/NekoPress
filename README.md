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
- Report issues here: https://github.com/NekoPress/NekoPress/issues/new/choose

## Report a bug (easy)

1. Open NekoPress and reproduce the issue once.
2. In app Info, click `Open Logs Folder`.
3. Keep the latest `nekopress-support-*.log` file.
4. Open: https://github.com/NekoPress/NekoPress/issues/new/choose
5. Choose `Bug report` and attach:
   - what happened
   - steps to reproduce
   - the latest support log file

## Security

- Electron hardening baseline: `contextIsolation: true`, `sandbox: true`, `nodeIntegration: false`
- Session permission handlers are explicit deny-by-default
- External URL policy is restricted to the official GitHub repository URL
- Support logs are local-only and masked (path/username tokens are hashed before write)
- Release assets include `SHA256SUMS.txt` for integrity verification

## Reliability

- Cancel policy: current in-flight file finishes safely, then remaining files are skipped
- Output writing uses atomic flow (`temp -> rename`) to reduce partial/corrupt output risk
- Startup orphan sweep cleans stale temp/session residues
- Preferences are normalized/migrated across schema updates
- Runtime compatibility guard blocks start on IPC contract mismatch

## Quality and Performance

- Quality-first pipeline with three presets: `High Detail`, `Balanced`, `Small Display`
- Conversion is tuned for visual quality retention with practical size reduction
- Automated gates are used before release (quality, privacy, update compatibility, stage checks)
- Throughput depends on CPU/storage/input complexity; policy prioritizes quality and stability over raw speed

## System Requirements

- OS: Windows 10/11 (x64)
- Architecture: x64
- RAM: 8 GB minimum (16 GB recommended for large batches)
- Storage: SSD recommended
- Distribution: portable executable (no installer)
