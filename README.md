# create-awesome-python-app — AUR package

[![Discord](https://img.shields.io/discord/1527933660764831825?label=Discord&logo=discord&logoColor=white)](https://discord.gg/bR5VyATgka)

AUR package for [create-awesome-python-app](https://github.com/Create-Python-App/create-python-app).

## Install (Arch Linux)

```bash
# using yay
yay -S create-awesome-python-app

# using paru
paru -S create-awesome-python-app
```

## Manual build

```bash
git clone https://github.com/Create-Python-App/aur-package.git
cd aur-package
makepkg -si
```

## Source

- AUR: https://aur.archlinux.org/packages/create-awesome-python-app
- GitHub: https://github.com/Create-Python-App/create-python-app
- PyPI: https://pypi.org/project/create-awesome-python-app/

## Version sync

This package mirrors the PyPI release of `create-awesome-python-app`.
`pkgver` in `PKGBUILD` must match the latest PyPI version; CI warns on drift
(`Version drift check (PyPI)` in `Validate PKGBUILD`).

## Troubleshooting

- `makepkg -si` fails on PGP/signature errors: this package ships no signatures;
  re-download the sdist URL from `PKGBUILD` and retry with a clean `src/`.
- `sha256sums` mismatch: a new PyPI sdist was published — bump `pkgver`,
  update the checksum, regenerate `.SRCINFO` (see below), and open a PR.
- `pip install` step fails offline: the `package()` step installs from the
  vendored sdist tarball; no network is required beyond downloading `source`.

## Release sync checklist (maintainers)

When a new version lands on PyPI:

1. Wait for the PyPI release to be visible.
2. Bump `pkgver` in `PKGBUILD` (reset `pkgrel=1`).
3. Update `sha256sums` with the new sdist checksum.
4. Regenerate `.SRCINFO` (`makepkg --printsrcinfo > .SRCINFO`).
5. Push via PR — `Validate PKGBUILD` must stay green.

## 👥 Contributors

<a href="https://github.com/Create-Python-App/aur-package/contributors">
  <img src="https://contrib.rocks/image?repo=Create-Python-App/aur-package"/>
</a>

Made with [contributors-img](https://contrib.rocks).
