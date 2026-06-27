# Security Policy

## Supported versions

| Version | Status |
| --- | --- |
| v0.1.5 | Current test release |
| v0.1.4 and older | Bug history only |

## Updater trust model

The updater is a separate application and should not silently install launcher builds.

- It reads the latest GitHub Release metadata.
- It downloads a signed update manifest.
- It verifies the manifest with the updater-bundled Ed25519 public key.
- It verifies SHA256 and file size before launching the installer.
- It still depends on the private signing key staying private. If that key is lost or exposed, rotate the key and publish a new updater build.

## Reporting a vulnerability

Open a private report if GitHub private vulnerability reporting is enabled. If it is not enabled, open a public issue without exploit details and state that you have a security concern.

Include:

- affected version
- Windows version and architecture
- installer type: LB or PF
- exact reproduction steps
- expected behavior
- actual behavior
- relevant logs or screenshots

Do not include malware samples, credentials, tokens, or personal files.

## Scope

In scope:

- installer overwrite behavior
- uninstall behavior
- startup shortcut behavior
- local category file handling
- local icon override handling
- accidental execution of unintended local files

Out of scope:

- attacks requiring physical access without a launcher-specific weakness
- vulnerability claims based only on unsigned binaries or SmartScreen reputation
- issues in third-party applications launched by this launcher

## Security expectations

This project is local-first and should not require a backend server to operate.

Security-sensitive changes should preserve:

- no secret keys in the repository
- no hidden downloader behavior
- predictable install and uninstall paths
- clear user-visible release assets
- minimal automatic startup behavior

## Unsafe versions

Bug versions are kept for traceability. Installing them on a daily-use PC can leave startup entries, settings, or files behind. Use a virtual machine or disposable test PC for historical version checks.
