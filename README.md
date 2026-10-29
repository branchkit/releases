# BranchKit releases

BranchKit's installers and update files. BranchKit's release workflow builds
each release here, and each one is published immutable: once a release is out,
its files and its tag cannot change. BranchKit's source is not in this
repository.

## What a release holds

| OS | File | For |
|---|---|---|
| macOS (Apple silicon) | `BranchKit-X.Y.Z-macos-arm64.dmg` | A first install |
| macOS (Apple silicon) | `BranchKit-X.Y.Z-macos-arm64.zip` | Updates |
| Windows (x64, arm64) | `BranchKit-X.Y.Z-windows-<arch>.zip` | Install and updates |
| Debian, Ubuntu | `branchkit_X.Y.Z_<arch>.deb` | Install; apt updates it |
| Fedora | `branchkit-X.Y.Z-1.<arch>.rpm` | Install; dnf updates it |
| Any Linux | `BranchKit-X.Y.Z-<arch>.AppImage` | Install and updates |

`SHA256SUMS` lists the SHA-256 of every other file.

## Checking a download

GitHub attests every immutable release. To check that a file came from a
release here, unchanged:

```bash
gh release verify-asset vX.Y.Z <file> --repo branchkit/releases
```

Or compare it with the release's `SHA256SUMS`:

```bash
shasum -a 256 -c SHA256SUMS --ignore-missing
```

`branchkit-cli app download`, which BranchKit's updater uses, makes both
checks itself.

## Reporting a problem

Report problems at
[github.com/branchkit/branchkit/issues](https://github.com/branchkit/branchkit/issues).
This repository has issues turned off.
