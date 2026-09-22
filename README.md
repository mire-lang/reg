# Owl registries

This directory contains local registry fixtures used while implementing and
testing Owl dependency resolution. It is not an installed registry and it is
not copied into `~/.owl/libs` automatically.

`mor/` is the Mire Official Registry fixture. Its index contains catalog
entries for Kioto, Mire and SDL, plus simulated SQLite and WASM entries. A
catalog-only entry is intentionally not installable: it has no archive hash
or signature yet. `owl export` must produce `publish.toml`, an archive, the
at least one SHA-256/SHA-512 hash and an Ed25519 signature before Owl accepts
it. If both hashes are present, Owl verifies both; the registry value remains
authoritative over publish metadata.

The registry format is directory-based so the index, package versions and
signatures can be updated independently without rewriting one large file.
