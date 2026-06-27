# Contributing

This repository is intended for developers and advanced users.

## Before contributing

Read:

- [README.md](./README.md)
- [SECURITY.md](./SECURITY.md)
- [CHANGELOG.md](./CHANGELOG.md)

## Development rules

- Keep the public download page simple for normal users.
- Keep source and build details in GitHub-facing documentation.
- Do not add copyrighted PC-room launcher assets, game logos, ad banners, or vendor UI screenshots unless they are properly licensed.
- Do not add telemetry, remote update checks, hidden downloaders, or background services without explicit documentation.
- Do not make installer or startup behavior harder to remove.

## Validation

Run these checks before proposing changes:

```powershell
npm run health
node --check app.js
node --check main.js
node --check kiosk-main.js
node --check category-folders.js
```

For installer changes, build in a disposable VM before testing on a real PC.

## Pull request expectations

Explain:

- what changed
- why it changed
- which edition is affected: LB, PF, or both
- whether installer behavior changed
- whether startup behavior changed
- what was tested
