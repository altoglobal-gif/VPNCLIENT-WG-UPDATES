# VPNCLIENT-WG Updates

Public update manifest and MSI artifact mirror for VPNCLIENT-WG for Windows.

This repository is intentionally separate from the private source repositories so the desktop client can check for updates without embedding a GitHub token.

## Current Channel

- Channel: `stable`
- Manifest: `latest.json`
- Latest version: `V.2026.24.5.0`
- Minimum in-app updater version: `V.2026.24.5.0`
- Baseline full installer: hosted outside this update repository in the main repository download area.

## Client Behavior

VPNCLIENT-WG reads `latest.json`, compares versions, downloads the listed update artifact, verifies file size and SHA256, then asks the local background helper service to schedule the update.

The client does not trust arbitrary downloads. The artifact path, file size, and SHA256 in the manifest are part of the release contract.

Clients older than `V.2026.24.5.0` do not contain the helper-backed auto update flow. They are routed to the full `V.2026.24.5.0` MSI hosted outside this repository. Versions from `V.2026.24.5.0` onward can consume patch/update artifacts from this update channel.

## Publishing Checklist

1. Build the Windows MSI from the private Windows source repository.
2. Compute SHA256 and size.
3. Update `latest.json`.
4. Copy only patch/update artifacts under `releases/<tag>/`.
5. Keep full installers outside this repository and host baseline/full installers in the main repository release/download area.
6. Commit and push this repository.
7. Verify the raw `latest.json` URL and update artifact URL return HTTP 200.
