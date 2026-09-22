# MOR local fixture

MOR means Mire Official Registry. This fixture is used by Owl tests before a
remote MOR endpoint is available.

Rules:

- `registry.toml` describes the registry and its trust policy.
- `index.toml` is the signed package catalog.
- `index.sig` signs the canonical index bytes.
- `packages/<name>/versions.toml` contains release records.
- At least one of SHA-256 or SHA-512 is required for installable releases.
- When both are present, Owl verifies both independently.
- Ed25519 public key and signature are required for installable releases.
- `catalog-only` and `simulated` records must never be installed.
