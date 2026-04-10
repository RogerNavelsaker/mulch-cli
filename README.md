# nixpkg-mulch

Nix packaging for `@os-eco/mulch-cli` using Bun and `bun2nix`.

## Package

- Upstream package: `@os-eco/mulch-cli`
- Pinned version: `0.6.3`
- Description: structured expertise files that accumulate over time, live in git, and work with any agent
- Installed binary: `mulch`
- Upstream executable invoked by Bun: `mulch`

## What This Repo Does

- Uses `bun.lock` and generated `bun.nix` as the dependency lock surface for Nix
- Builds the upstream package as an internal Bun application with `bun2nix`
- Exposes only the canonical binary name `mulch`
- Provides a manifest sync script for updating the pinned npm metadata

## Files

- `flake.nix`: flake entrypoint
- `nix/package.nix`: Nix derivation
- `nix/package-manifest.json`: pinned package metadata and exposed binary name
- `scripts/sync-from-npm.ts`: updates pinned npm metadata without changing the canonical output binary

## Notes

- The default `out` output installs the longform binary name `mulch`.
- The shortform name `ml` is available as a separate Nix output, not in the default `out` output.
