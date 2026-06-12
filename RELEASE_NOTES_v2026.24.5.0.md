# VPNCLIENT-WG V.2026.24.5.0 Update Mirror

This update mirror defines the `V.2026.24.5.0` helper-backed auto update baseline.

## Artifact

- File: full installer is published outside this update repository.
- SHA256: `A852BEC88368B14B6042B6D51DC3F44AE51A32CB16DE6D8170AEDCE9D7CB4375`
- Size: `95780864`

## Manifest

- `latest.json` points stable clients to `V.2026.24.5.0`.
- Minimum direct in-app update version is `V.2026.24.5.0`.
- Clients older than `V.2026.24.5.0` must install this baseline manually once before future helper-backed auto updates can run inside the app.

## Expected Client Flow

1. Check `latest.json`.
2. Download the update artifact.
3. Verify file size and SHA256.
4. Ask `VpnClientWgHelper` to schedule the MSI patch update.
5. Close VPNCLIENT-WG so Windows Installer can replace files cleanly.
