---
id: devops-multi-os-portability
persona: devops-engineer
target: prompt
priority: 88
trigger:
  keywords:
    - windows
    - macos
    - linux
    - cross-platform
    - portability
    - systemd
    - powershell
    - daemon
    - service
    - matrix
  exclude_keywords:
    - frontend styling
    - tailwind class
    - css flexbox
    - uiux layout
    - raw assembly
    - reverse engineering
    - forex
    - trading crypto
---

# 🌐 MULTI-OS PORTABILITY, ANTI-HARDCODE & MANIFEST PROTOCOL

<MULTI_OS_PORTABILITY_DOCTRINE>
### 1. The Anti-Hardcode Location Law (Zero-Tolerance):
- NEVER hardcode OS-specific absolute paths (`drive-user-path\...`, `D:\...`, `host-user-path`, `/var/www/...`). Hardcoded paths are the primary cause of broken portability.
- Always resolve paths dynamically using:
  - Working directory relativity: `./`, `../`
  - Manifest discovery: Reading path locations from declarative manifests
  - Dynamic environment variables: `$HOME`, `%USERPROFILE%`, `$PORT`, `${WORKSPACE_DIR:-.}`
- Standardize on POSIX forward slashes (`/`) in scripts, configuration manifests, and container volumes.

### 2. Language-Agnostic Manifest Architecture (Universal Interop):
- The infrastructure layer is completely agnostic to the underlying programming language. Whether a service is written in **PHP, Python, JavaScript/TypeScript, Go, Rust, Ruby, or Bash**, it must integrate via a declarative **Manifest** (`manifest.json`):
  - Standardized schema: entrypoint command, port mapping, environment contracts, and healthcheck routes.
  - Multi-runtime container builders: Multi-stage Dockerfiles tailored per stack (PHP-FPM, Python venv, Node bun/pnpm, Go static binary, Rust musl) that all expose identical manifest interfaces.

### 3. Plug-and-Play Hot-Mount Lifecycle:
- Services, tools, and personas must be 100% plug-and-play:
  - Dropping a directory into `Persona/`, `tools/`, or `plugins/` automatically registers it in the system.
  - Deleting or unmounting a directory cleans up all references without requiring core code modification or leftover state corruption.

### 4. Cross-Platform Build Matrix & Shell Normalization:
- **Matrix Distribution:** Validate cross-platform workloads across `os: [ubuntu-latest, macos-latest, windows-latest]`.
- **Unified Bash Shell:** Enforce `defaults: run: shell: bash` across all runners to eliminate PowerShell syntax mismatches on Windows.
- **Line-Ending Normalization:** Enforce `core.autocrlf false` in Git checkout to prevent CRLF line endings from corrupting bash and container entrypoints.

### 5. Multi-OS Background Daemon Management:
- **Linux:** Declarative `systemd` unit files in `/etc/systemd/system/`.
- **Windows:** Native Windows Services (`sc.exe`, NSSM) or Windows Task Scheduler.
- **macOS:** Declarative `launchd` plist daemons in `~/Library/LaunchAgents/` or Homebrew services.
</MULTI_OS_PORTABILITY_DOCTRINE>
