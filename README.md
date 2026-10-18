# z0mbix Homebrew tap

Homebrew packages for software by [z0mbix](https://github.com/z0mbix).

## Install

```sh
brew install z0mbix/tap/kqt
```

Or add the tap first, then install any of its packages:

```sh
brew tap z0mbix/tap
brew install kqt
```

Update packages with `brew update` followed by `brew upgrade`.

## Packages

| Formula | Description | Platforms |
| --- | --- | --- |
| [kqt](https://github.com/z0mbix/kqt) | A keyboard-first Kubernetes browser | macOS Apple Silicon and Intel |

Formulae install published binaries and verify their SHA-256 checksums. No Go
compiler or kubectl installation is required for kqt.

## Publishing

Each software repository owns its release process and updates its formula here
after publishing a stable release. kqt generates `Formula/kqt.rb` from its
published archives and `SHA256SUMS` using `scripts/homebrew_formula.py` in
[z0mbix/kqt](https://github.com/z0mbix/kqt). Prereleases do not update this tap.

Each publishing repository uses its own write-enabled deploy key scoped to this
tap. The private key stays in that repository's Actions secrets. Do not reuse
personal SSH keys or account-wide access tokens for publishing.

The tap's CI installs and tests every formula on Apple Silicon and Intel macOS.
Add further command-line tools under `Formula/`; macOS app casks can be added
under `Casks/` when needed.
