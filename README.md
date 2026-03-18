# mulch-cli

Nix packaging for `@os-eco/mulch-cli` using Bun and `bun2nix`.

## Package

- Upstream package: `@os-eco/mulch-cli`
- Pinned version: `0.6.3`
- Installed binary: `mulch`
- Upstream executable invoked by Bun: `mulch`

## What this repo does

- Uses `bun.lock` and generated `bun.nix` as the dependency lock surface for Nix
- Builds an internal Bun application package with `bun2nix`
- Exposes only the canonical binary name `mulch`
- Provides a GitHub Actions workflow that can sync the pinned npm version

## Files

- `flake.nix`: flake entrypoint
- `nix/package.nix`: Nix derivation
- `nix/package-manifest.json`: pinned package metadata and exposed binary name
- `scripts/sync-from-npm.ts`: updates pinned npm metadata without changing the canonical output binary

## Usage

```bash
nix build
./result/bin/mulch --help
```

## Notes

- Short aliases such as `ml` are intentionally not installed by this package.
- If you want a short alias, create it in your shell configuration or Flox environment.
