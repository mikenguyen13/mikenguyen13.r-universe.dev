# mikenguyen13.r-universe.dev

Registry for <https://mikenguyen13.r-universe.dev>. R-universe reads
`packages.json` and builds each listed package from its GitHub repository,
with binaries for Windows, macOS, Linux and WebAssembly.

| Package | Source | Why it is here |
|---|---|---|
| causalverse | [mikenguyen13/causalverse](https://github.com/mikenguyen13/causalverse) | Not on CRAN; this is its install route |
| regsensitivity | [mikenguyen13/regsensitivity](https://github.com/mikenguyen13/regsensitivity) | On CRAN; this serves the development version |
| synthdid | [synth-inference/synthdid](https://github.com/synth-inference/synthdid) | Imported by causalverse and not on CRAN, so it has to be in the same repository for installs to resolve |
| MCPanel | [susanathey/MCPanel](https://github.com/susanathey/MCPanel) | Suggested by causalverse (the `mc` estimator) and not on CRAN |

## Install

```r
install.packages(
  c("causalverse", "regsensitivity"),
  repos = c("https://mikenguyen13.r-universe.dev", "https://cloud.r-project.org")
)
```

## Maintenance

- Add a package: append `{"package": ..., "url": ...}` to `packages.json`.
- synthdid: causalverse's `Remotes:` pins commit `70c1ce3`, which is also the
  tip of synthdid's `master` (no commits since January 2024). If synthdid's
  master moves and the pin matters, add `"branch": "<commit or branch>"` to
  its entry.
