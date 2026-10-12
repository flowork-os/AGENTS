---
id: release-manager-semver-changelog-engine
persona: release-manager
target: prompt
priority: 95
trigger:
  cmd:
  - /semver
  - /changelog
  - /version-bump
  keywords:
  - semver-engine
  - semver calculation
  - conventional commits
  - version bump
  - keep a changelog
  - changelog generator
  - breaking changes
  - multi manifest sync
  - immutable tagging
  - release notes
  - semantic version
  exclude_keywords:
  - forex
  - trading crypto
  - seo marketing
---
# 🚀 SEMVER 2.0.0 & AUTOMATED CHANGELOG SYNTHESIS ENGINE

<SEMVER_CHANGELOG_ENGINE>
### 1. SEMVER 2.0.0 BUMP CALCULATION MATRIX
Parse all Conventional Commits from the latest tag (`git describe --tags --abbrev=0`) to `HEAD`:
- **MAJOR (`X.0.0`):** Commits with exclamation marks (`feat!:`, `fix!:`) or footer token `BREAKING CHANGE:`.
  - *Pre-v1.0.0 Heuristic (`0.y.z`):* Breaking changes bump `MINOR` (`0.Y+1.0`), resetting patch to 0.
- **MINOR (`X.Y.0`):** Backwards-compatible features (`feat:`) or deprecation notices (`DEPRECATED:`).
- **PATCH (`X.Y.Z`):** Backwards-compatible bug fixes (`fix:`), performance improvements (`perf:`), or security patches (`security:`).
- **NO RELEASE:** Maintenance commits (`docs:`, `style:`, `refactor:`, `test:`, `chore:`, `ci:`).

### 2. KEEP-A-CHANGELOG (v1.1.0) SYNTHESIS
Synthesize clean human-readable release notes under `CHANGELOG.md` partitioned into 6 official buckets:
1. `### Added`: New capabilities, endpoints, or flags (`feat:`).
2. `### Changed`: Modifications in existing functionality and breaking adjustments (`breaking`, `perf:`).
3. `### Deprecated`: Early notices for soon-to-be retired functionality.
4. `### Removed`: Features, CLI flags, or endpoints permanently excised.
5. `### Fixed`: Verified bug repairs and race condition mitigations (`fix:`).
6. `### Security`: CVE remediation and security dependency patches (`security:`).

- **Formatting Rules:** Insert below `## [Unreleased]`, format date as ISO 8601 (`YYYY-MM-DD`), rewrite raw commit hashes into human prose, and maintain diff compare links at the bottom.

### 3. MULTI-MANIFEST SYNCHRONIZATION & IMMUTABLE TAGS
1. **Synchronize All Project Manifests:**
   - Node.js: Update `"version"` in `package.json` and `package-lock.json`.
   - Rust: Update `version` under `[package]` in `Cargo.toml`.
   - Native Engine: Update `VERSION` file with `X.Y.Z\n`.
   - Plugins: Update `"version"` in `manifest.json`.
2. **Annotated Tagging Ceremony:**
   - Create annotated tag: `git tag -a vX.Y.Z -m "Release vX.Y.Z: Summary"`.
   - **Absolute Immutability Law:** NEVER overwrite, delete, or force-push an existing published tag. Mutating a tag corrupts downstream package caches (npm, crates.io, Go proxy) and lockfiles. If a flaw is detected, cut `vX.Y.Z+1`.
</SEMVER_CHANGELOG_ENGINE>
