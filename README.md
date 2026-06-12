# VPNCLIENT-WG Updates

Public update manifest and MSI artifact mirror for VPNCLIENT-WG for Windows.

This repository is intentionally separate from the private source repositories so the desktop client can check for updates without embedding a GitHub token.

## Current Channel

- Channel: `stable`
- Manifest: `latest.json`
- Latest version: `V.2026.24.5.0`
- Artifact: `releases/v2026.24.5.0/VPNCLIENT-WG-V.2026.24.5.0-win-x64.msi`

## Client Behavior

VPNCLIENT-WG reads `latest.json`, compares versions, downloads the listed MSI, verifies file size and SHA256, then asks the local background helper service to schedule the MSI patch update.

The client does not trust arbitrary downloads. The artifact path, file size, and SHA256 in the manifest are part of the release contract.

## Publishing Checklist

1. Build the Windows MSI from the private Windows source repository.
2. Compute SHA256 and size.
3. Update `latest.json`.
4. Copy the MSI under `releases/<tag>/`.
5. Commit and push this repository.
6. Verify the raw `latest.json` URL and MSI URL return HTTP 200.
