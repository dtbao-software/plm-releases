# Product Lifecycle Management — Releases

[![Latest release](https://img.shields.io/github/v/release/dtbao-software/plm-releases?label=latest&color=3b5bdb)](https://github.com/dtbao-software/plm-releases/releases/latest)
![Platform](https://img.shields.io/badge/platform-Windows%2011%20x64-0078d4)
![License](https://img.shields.io/badge/license-MIT-green)

**Product Lifecycle Management (PLM)** is a single-user Windows desktop app that
tracks a hardware product from requirements to end of life: requirements, main
ICs, HW + BOM, FW and SW, the state of every part in one pipeline, what was tested
on which part versions, and which part versions shipped together.

This repository holds **release files only** — installers, their update
signatures and the auto-update manifest. The source code lives in a private
repository.

## Download and install

1. Open the [latest release](https://github.com/dtbao-software/plm-releases/releases/latest).
2. Download `Product Lifecycle Management_<version>_x64-setup.exe`.
3. Run it. It installs for the current user only, with no admin prompt.

The installer is not code-signed yet, so Windows SmartScreen may warn on first
install: choose *More info* → *Run anyway*.

**Requirements:** Windows 11 x64 with the WebView2 runtime (included in Windows 11).

## Version and updates

- The badge above always shows the latest version. Versions follow
  [Semantic Versioning](https://semver.org/) with a `v` prefix (`vMAJOR.MINOR.PATCH`);
  below `v1.0.0` the data format and interfaces may still change between minor
  versions.
- From `v0.2.0` on, the app checks this repository for a newer version after it
  starts and then every 5 minutes. When one is found, an update icon appears at
  the right of the header. Nothing installs on its own: click the icon, read the
  release notes, then *Install and restart* or *Later*.
- An install waits until no long operation (clone, import, copy, backup, restore)
  is running, so it never cuts one in half.
- Every update is signed; the app refuses an update whose signature does not
  match. Offline, the app works normally and simply checks again later.
- `v0.1.0` has no updater: install the first updater version over it by hand, once.

Each release lists its changes in its release notes.

## Features

Status: **Available** — in a published release · **Next** — in the next release ·
**Planned** — specified, not built yet. The MVP is the first five planned groups.

### Delivery and app shell

| Feature | Status |
|---|---|
| Per-user Windows installer, Start menu entry, clean uninstall | Available (v0.1.0) |
| Browser behaviour of the web view switched off (reload, back/forward, print, find, context menu) | Available (v0.1.0) |
| App logo and icons | Next (v0.2.0) |
| Splash screen while the app starts | Next (v0.2.0) |
| Signed auto update with an in-app update icon and release notes | Next (v0.2.0) |
| Light and dark appearance following Windows | Next (v0.2.0) |

### Products and settings — MVP

| Feature | Status |
|---|---|
| Products: create, edit, archive, delete (app data only); slug suggested from the name | Planned |
| Sidebar with each product's stage, progress, and stale, blocked and overdue counts | Planned |
| Settings: workspace root and remote organisation per part kind, fabrication folder, theme (System · Light · Dark) | Planned |
| Start with Windows (off by default) | Planned |
| Every change recorded in an audit log, attributed to human, agent or system | Planned |

### Parts and workspaces — MVP

| Feature | Status |
|---|---|
| Register an existing git workspace as a HW, FW or SW part; scan the root for unregistered folders | Planned |
| *Initialize git here* for a folder without git (shows file count and size first) | Planned |
| Clone a repository from the configured organisation or any git URL, then register it | Planned |
| Read version (latest tag, or a manual version), `HEAD` commit, remote URL and clean state — read-only | Planned |
| Open a part in Explorer, VS Code, the browser (remote) or its CAD project | Planned |
| Pipeline tab: every part of a product in one view, with a detail drawer | Planned |
| Scaffold a new part folder with git, README and `.gitignore`; optionally create its private GitHub repo | Planned |

### Status, dependencies and lifecycle — MVP

| Feature | Status |
|---|---|
| Part status Not started → In progress → Testing → Released, with Blocked and a reason | Planned |
| Dependencies between parts; *Stale* when a dependency's version changes | Planned |
| Release gate per part: dependencies released, not blocked or stale, known version, clean tree, HW package present | Planned |
| Released version pinned to a commit; *Pending* when the workspace moves past it | Planned |
| Product stages Concept → EVT → DVT → PVT → MP → EOL with automatic gate criteria and custom gate items | Planned |
| History tab: filter the audit log by entity, actor and date | Planned |

### Requirements, tasks and tests — MVP

| Feature | Status |
|---|---|
| Requirements with priority and category; requirements × parts matrix | Planned |
| Tasks (todo · doing · done) with estimate, start and due dates, optional requirement link | Planned |
| Import tasks from XLSX or CSV with column mapping and preview | Planned |
| Test runs that record every part's version and commit, with Pass, Fail or Skip per requirement | Planned |
| Verified requirements and coverage from the latest test results; progress per part and product | Planned |
| MCP server (`plm-mcp`) so AI agents can read the pipeline and add or update tasks, even while the app is closed | Planned |

### Main ICs, HW packages and BOM — MVP

| Feature | Status |
|---|---|
| Main ICs entered by hand | Planned |
| HW release packages: fabrication outputs, BOM and pick-and-place copied into a named package folder | Planned |
| BOM table from a package, columns detected from Altium and KiCad headers | Planned |
| BOM diff between two packages (added, removed, MPN and quantity changes) | Planned |
| Main IC ↔ BOM sync with warnings and suggested fixes | Planned |

### Releases and backup — MVP

| Feature | Status |
|---|---|
| Release bundles that pin every part's released version, commit and HW package; compare and withdraw | Planned |
| Backup of the app data to a private GitHub repository (on close, daily, or on demand) and restore | Planned |

### After the MVP

| Feature | Status |
|---|---|
| Online part lookup by MPN (DigiKey, Mouser, LCSC): lifecycle, datasheet, prices, stock | Planned |
| Price book, its import from XLSX or CSV, and BOM cost per board and per build | Planned |
| BOM lifecycle check: NRND, EOL and out-of-stock lines | Planned |
| ECO (engineering change orders) required to change released parts in PVT and MP | Planned |
| Schedule tab: planned against actual stage dates, overdue and upcoming tasks | Planned |
| Attachments: labelled links to files or URLs on requirements, parts, ICs, releases, ECOs and test runs | Planned |
| Reports: self-contained HTML product report; BOM and requirement export to XLSX or CSV | Planned |

## Privacy

Everything is stored locally in the app's data folder. API tokens are kept in
Windows Credential Manager and never written to the database, backups, logs or
reports. The app talks only to GitHub, the part-lookup providers, and the git
remotes you clone from.

## License

MIT © 2026 dtbao
