# Product Lifecycle Management

[![Version](https://img.shields.io/github/v/release/dtbao-software/plm-releases?label=version&color=3b5bdb)](https://github.com/dtbao-software/plm-releases/releases/latest)
![Platform](https://img.shields.io/badge/platform-Windows%2011%20x64-0078d4)
![License](https://img.shields.io/badge/license-MIT-green)

Windows desktop app that tracks a hardware product from requirements through
main ICs, HW, BOM, FW and SW in one pipeline.

This repository holds release files only: installers and auto-update files.

## Install

Download `Product Lifecycle Management_<version>_x64-setup.exe` from the
[latest release](https://github.com/dtbao-software/plm-releases/releases/latest)
and run it. If SmartScreen warns, choose *More info* → *Run anyway*.

## Version and updates

- Versions follow [Semantic Versioning](https://semver.org/): `vMAJOR.MINOR.PATCH`.
  Each release lists its changes in its release notes.
- From `v0.2.0` on, the app checks for a new version on its own. When one is
  found, an update icon appears in the header: click it, then
  *Install and restart*. Nothing installs without your click.
- Updates are signed; the app refuses one whose signature does not match.
- `v0.1.0` has no updater: install `v0.2.0` over it by hand, once.

## License

MIT © 2026 dtbao
