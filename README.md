# z0mbix Homebrew tap

Homebrew packages for software by [z0mbix](https://github.com/z0mbix).

## Install

```sh
brew install z0mbix/tap/kqt
brew install z0mbix/tap/fmn
brew install z0mbix/tap/rolecule
```

Or add the tap first, then install any of its packages:

```sh
brew tap z0mbix/tap
brew install z0mbix/tap/kqt
```

Update packages with `brew update` followed by `brew upgrade`.

## Packages

| Formula | Description | Platforms |
| --- | --- | --- |
| [kqt](https://github.com/z0mbix/kqt) | A keyboard-first Kubernetes browser | macOS Apple Silicon and Intel |
| [fmn](https://github.com/z0mbix/fmn) | Local-first shell history manager for Fish, Zsh, and Bash | macOS and Linux, ARM64 and AMD64 |
| [rolecule](https://github.com/z0mbix/rolecule) | Test Ansible roles in Docker or Podman containers | macOS and Linux, ARM64 and AMD64 |

Formulae install published binaries and verify their SHA-256 checksums. No Go
compiler or kubectl installation is required for kqt.
Rolecule requires Docker or Podman, Ansible, and a verifier such as Goss to run role tests.

## Publishing

Each software repository owns its release process and updates its formula here
after publishing a stable release. kqt generates `Formula/kqt.rb` from its
published archives and `SHA256SUMS` using `scripts/homebrew_formula.py` in
[z0mbix/kqt](https://github.com/z0mbix/kqt). Prereleases do not update this tap.
Rolecule generates `Formula/rolecule.rb` from its published macOS and Linux
archives and versioned `SHA256SUMS` using `scripts/homebrew_formula.py` in
[z0mbix/rolecule](https://github.com/z0mbix/rolecule).

fmn generates `Formula/fmn.rb` from its published macOS and Linux archives and
`sha256.sum` using `scripts/homebrew_formula.py` in
[z0mbix/fmn](https://github.com/z0mbix/fmn). Its formula checks the installed
version and runs SQLite diagnostics in an isolated test directory.

Each publishing repository uses its own write-enabled deploy key scoped to this
tap. The private key stays in that repository's Actions secrets. Do not reuse
personal SSH keys or account-wide access tokens for publishing.

The tap's CI installs and tests every formula on Apple Silicon and Intel macOS.
Add further command-line tools under `Formula/`; macOS app casks can be added
under `Casks/` when needed.
