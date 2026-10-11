# Apple tvOS compatibility branch

Based on upstream `spacejam/sled` tag `v0.34.7`
(`d81865d07f07910133877915b57abf0c52d5756b`).

- Upgrade `parking_lot` from 0.11 to 0.12.5, allowing the maintained
  `parking_lot_core` 0.9 Apple backend to support tvOS.
- Import `size_of`/`align_of` explicitly and remove redundant qualifications
  for modern Rust's prelude. Preserve the upstream lint policy.
- Keep storage format, database algorithms and public API unchanged.

Validation: `cargo test --lib` (30 tests), netgrid legacy-to-fork-to-legacy
on-disk transaction regression, and default-feature Apple builds.
Use an immutable Git revision in downstream manifests.
