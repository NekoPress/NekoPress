# NekoPress

Quality-first image compression engine for Windows portable use.

## Download

Download the latest build from:

- Releases: `https://github.com/NekoPress/NekoPress/releases/latest`

If the repository is newly created and has no release yet, use:

- `https://github.com/NekoPress/NekoPress/releases`

## Supported Environment

- Windows 10/11 (64-bit)
- Portable mode (no installer required)

## Quick Start

1. Download release asset.
2. (Recommended) Verify SHA256 hash with `SHA256SUMS.txt`.
3. Unzip if needed.
4. Run `NekoPress-<version>.exe`.

## Checksum Verification (PowerShell)

```powershell
Get-FileHash ".\\NekoPress-<version>.exe" -Algorithm SHA256
```

Compare output hash with `SHA256SUMS.txt`.

## Privacy

- NekoPress processes files locally on your machine.
- No cloud upload is required for conversion.

## Input Support and Output Guarantees

- Input support: standard non-animated JPG/JPEG and single-frame PNG. Some valid profiled RGB/greyscale/CMYK JPG, verified SDR-base gain-map JPEG, and 16-bit PNG inputs may also open when the current decoder can read them. Unprofiled CMYK, identifiable native HDR, damaged/conflicting color metadata, and gain maps without a trustworthy SDR base direction are rejected per file rather than converted with uncertain color.
- Output guarantees: accepted re-encoded outputs are generated as SDR/sRGB-oriented artifacts for practical web-upload use. They strip EXIF/XMP/IPTC/ICC by default. Supported profiled input is color-managed to sRGB before profile removal. Same-format copied fallback also removes copied metadata and keeps only a minimal orientation tag when that is required for display correctness. Accepted SDR-base gain-map JPEG inputs are re-encoded from their verified SDR base image; after successful conversion, result details state that the gain map was not retained. NekoPress does not reconstruct HDR or tone-map it to SDR on this path. ICC/profile retention, HDR gain-map preservation, and 16-bit PNG output preservation are not guaranteed in the current release line.
- Color trust boundary: untagged RGB/greyscale web images are treated as sRGB. No converter can recover a different authoring gamut when the file contains no trustworthy color description.
- Keep original files if exact metadata, ICC/profile retention, HDR behavior, or bit-depth preservation matters.

## Known Notes

- For drag-and-drop on Windows, run app in normal user mode.
- Very large batches may take time (quality-first processing).

## Report a Bug

1. Reproduce the issue once.
2. Open app Info and click `Open Logs Folder`.
3. Keep the newest `nekopress-support-*.log`.
4. Open issue form:
   - `https://github.com/NekoPress/NekoPress/issues/new/choose`
5. Choose `Bug report` and attach the log file.

## Security Reporting

Please report security issues via the process in `SECURITY.md`.
