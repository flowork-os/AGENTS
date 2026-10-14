---
trigger_id: "SYS-TRIG-RUST-WORKSPACE"
name: "Rust Workspace Compiler & Borrow Checker Policy"
scopes:
  - "specialist_solo"
  - "specialist_group"
  - "default_solo"
categories:
  - "CAT-005"
internal_conditions:
  workspace:
    has_files: ["Cargo.toml"]
  file_context:
    extension: [".rs"]
  environment:
    has_binaries: ["cargo"]
---
<RUST_WORKSPACE_POLICY>
[RUST ECOSYSTEM & SOURCE MUTATION DETECTED]
1. COMPILE AUDIT: Run `cargo check` or `cargo test` in the crate directory immediately following source modifications.
2. ZERO WARNINGS: Resolve borrow checker, lifetime, and unwrap defects cleanly; do not leave dead code unaddressed.
3. PRESERVE LOCKS: Strictly preserve any locked lines containing `@lock` or `@freez` markers.
</RUST_WORKSPACE_POLICY>
