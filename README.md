# Korean-style PC Room Launcher

Developer-facing source and release workspace for a local Windows PC-room style launcher.

## Normal users

Normal users should not build from this repository.

Use the public download page instead:

https://skqkwjsjsywhbd77282-arch.github.io/korean-style-pc-room-launcher/

Recommended files:

- LB installer: login screen plus launcher
- PF installer: launcher only

The source ZIP and repository files are intended for developers, reviewers, and advanced users.

## Project status

This is an early Windows x64 prototype.

- Tested target: Windows x64, 1920x1080
- Unverified: Windows 32-bit, Windows ARM64, non-standard display scaling
- Known limitation: many third-party app shortcuts and icons are still compatibility-sensitive
- Bug versions are kept for traceability only and should not be installed on daily-use PCs

## Repository role

This repository is intentionally more technical than the public download page. It exists for:

- source review
- release asset verification
- installer behavior review
- security policy and issue tracking
- advanced local builds

## Editions

| Edition | Purpose |
| --- | --- |
| LB | Login screen plus launcher |
| PF | Launcher only |
| UP | Separate updater application |

## Release naming

Release assets use this pattern:

```text
Codex-PCBang-Launcher-Setup-LB2026062715-v0.1.5-win-x64.exe
Codex-PCBang-Launcher-Setup-PF2026062715-v0.1.5-win-x64.exe
Codex-PCBang-Updater-Setup-UP2026062715-v0.1.5-win-x64.exe
```

- `LB` and `PF` identify the edition.
- `UP` identifies the separate updater application.
- `2026062715` is the update stamp in `yyyyMMddHH` format.
- `v0.1.5` is the application version.

## Build prerequisites

- Windows 11 x64
- Node.js compatible with the local project
- npm
- Electron Builder dependencies installed through `npm install`

## Local development

```powershell
npm install
npm run health
npm run start:kiosk
```

## Build commands

```powershell
npm run dist:win:x64
npm run dist:updater
npm run dist:site-assets
```

The project currently treats x64 as the primary build. ia32 and ARM64 are listed as future or unverified targets.

## Security

Read [SECURITY.md](./SECURITY.md) before reporting or testing vulnerabilities.

Do not test installer cleanup, startup behavior, or shell integration on a primary daily-use PC unless you are prepared to restore the system.

The updater is intentionally separate from the launcher. It verifies a signed update manifest with an embedded Ed25519 public key, then verifies the downloaded installer SHA256 before launching the installer. The private signing key must stay outside the public repository.

## License

See [LICENSE](./LICENSE).
