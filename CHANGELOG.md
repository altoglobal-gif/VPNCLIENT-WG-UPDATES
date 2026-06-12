# Changelog

## V.2026.24.5.0 - 2026-06-12

### Added

- Updated `latest.json` for the `V.2026.24.5.0` helper-backed auto update baseline.
- Added update repository README and release note documentation.

### Changed

- The manifest now supports the client-side auto update flow where VPNCLIENT-WG downloads, verifies, and asks the helper service to schedule installation.
- Raised the minimum in-app updater version to `V.2026.24.5.0` so older clients are routed to manual update instead of opening raw MSI links.
- Removed full MSI installers from the update repository. Full installers must be published outside this repository.
- Pointed the bootstrap manifest artifact to the full `V.2026.24.5.0` MSI hosted in the main repository so older clients can download the baseline installer.

## V.2026.24.4.1 - 2026-06-12

### Added

- Published the `V.2026.24.4.1` Windows MSI for patch update discovery.
- Updated `latest.json` to point to the `V.2026.24.4.1` raw MSI artifact.

### Notes

- This version still required the client to open the MSI/download URL manually.
