Deprecated in favor of https://github.com/haskell/ghcup

## ghc-switch

`ghc-switch` manages the installation of multiple versions of `ghc` and related binaries. Specifically, it:

- Downloads, configures, and installs (if necessary) a pre-built GHC tarball from `downloads.haskell.org` into `~/.ghc-switch/`.
- Creates symlinks in `~/.local/bin/` as necessary.

---

### Motivation

You should use `ghc-switch` if:
  - You don't use `stack`, which is capable of downloading and installing `ghc` itself.
  - You _do_ use `stack`, but would still like a convenient way to switch between global `ghc` installations, or are annoyed by having to `stack exec`.
  - Your OS package manager is insufficient (as on Arch Linux, for example, due to the rolling-release schedule precluding multiple versions of `ghc` existing simultaneously).

---

### Usage

```
$ ghc-switch 8.2.2
$ ghc --version
The Glorious Glasgow Haskell Compilation System, version 8.2.2

$ ghc-switch 8.0.2
$ ghc --version
The Glorious Glasgow Haskell Compilation System, version 8.0.2
```

Namespaced versions are also installed:

```
$ ghc-8.2.2 --version
The Glorious Glasgow Haskell Compilation System, version 8.2.2
$ ghc-8.0.2 --version
The Glorious Glasgow Haskell Compilation System, version 8.0.2
```
