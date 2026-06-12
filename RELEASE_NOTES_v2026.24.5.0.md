# VPNCLIENT-WG V.2026.24.5.0 Update Mirror

This update mirror publishes the Windows MSI used by the VPNCLIENT-WG helper-backed auto update flow.

## Artifact

- File: `releases/v2026.24.5.0/VPNCLIENT-WG-V.2026.24.5.0-win-x64.msi`
- SHA256: `A852BEC88368B14B6042B6D51DC3F44AE51A32CB16DE6D8170AEDCE9D7CB4375`
- Size: `95780864`

## Manifest

- `latest.json` points stable clients to `V.2026.24.5.0`.
- Minimum direct patch version remains `V.2026.24.3.0`.
- The artifact URL uses `raw.githubusercontent.com` so the client can download without GitHub authentication.

## Expected Client Flow

1. Check `latest.json`.
2. Download the MSI.
3. Verify file size and SHA256.
4. Ask `VpnClientWgHelper` to schedule the MSI patch update.
5. Close VPNCLIENT-WG so Windows Installer can replace files cleanly.
