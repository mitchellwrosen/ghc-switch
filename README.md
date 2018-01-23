## ghc-switch

`ghc-switch` manages the installation of multiple versions of `ghc` and related binaries. Specifically, it:

- Downloads, configures, and installs (if necessary) a pre-built GHC tarball from `downloads.haskell.org` into `~/.ghc-switch/`.
- Downloads, configures, and installs (if necessary) a compatible version of `cabal-install` from `hackage.haskell.org` into `~/.ghc-switch/`.
- Creates symlinks in `~/.local/bin/` as necessary.

---

### Motivation

You should use `ghc-switch` if:
  - You don't use `stack`, which is capable of downloading and installing `ghc` itself.
  - You _do_ use `stack`, but would still like a convenient way to switch between global `ghc` installations, or are annoyed by having to `stack exec`.
  - Your OS package manager is insufficient (as on Arch Linux, for example, due to the rolling-release schedule precluding multiple versions of `ghc`).

---

### Usage

```
$ ghc-switch 8.2.2
$ ghc --version
The Glorious Glasgow Haskell Compilation System, version 8.2.2
$ cabal --version
cabal-install version 2.0.0.1
compiled using version 2.0.1.0 of the Cabal library

$ ghc-switch 8.0.2
$ ghc --version
The Glorious Glasgow Haskell Compilation System, version 8.0.2
$ cabal --version
cabal-install version 1.24.0.2
compiled using version 1.24.2.0 of the Cabal library
```

Here is the full list of executable programs that (may) change when switching between versions of `ghc`:

- `cabal`
- `ghc`
- `ghci`
- `ghc-pkg`
- `haddock`
- `hp2ps`
- `hpc`
- `hsc2hs`
- `runghc`
