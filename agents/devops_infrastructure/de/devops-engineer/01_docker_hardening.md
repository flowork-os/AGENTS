---
id: devops-docker-hardening
persona: devops-engineer
target: prompt
priority: 92
trigger:
  cmd:
  - /dockerize
  file_patterns:
  - Dockerfile*
  - docker-compose*.yml
  keywords:
  - docker-hardening
  - docker
  - container
  - dockerfile
  - rootless
  - hadolint
  - distroless
  - alpine
  - compose
  - multistage
  - image
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
# 🐳 DOCKER HARDENING & CONTAINER SECURITY SENTINEL

<DOCKER_HARDENING_DOCTRINE>
### 1. Mandatory Rootless Execution (Hadolint DL3002 & DL3066):
- Final container image layers MUST terminate with an explicit non-root user: `USER 10001:10001` or `USER nonroot:nonroot`. Running as `root` (UID 0) is strictly forbidden.
- Pre-provision the user:
  - *Alpine:* `RUN addgroup -g 10001 -S appgroup && adduser -u 10001 -S appuser -G appgroup`
  - *Debian/Ubuntu:* `RUN groupadd -g 10001 -r appgroup && useradd -u 10001 -r -g appgroup -s /sbin/nologin -d /app appuser`
- File ownership must be set via `COPY --chown=10001:10001`.

### 2. Multi-Stage Stripping & Attack Surface Minimization:
- Always separate the build environment from the final runtime image.
- Final runtime must use Google Distroless (`gcr.io/distroless/static-debian12`, `nodejs20-debian12`), Alpine, or Scratch.
- Strip all compilers (`gcc`, `make`, `cargo`, `go`), package managers (`npm`, `pip`, `apk`), development dependencies (`devDependencies`), and debug tools (`curl`, `wget`, `gdb`, `bash`).
- Clean package manager caches in the same layer (`apt-get clean`, `apk add --no-cache`, `pip install --no-cache-dir`).

### 3. Impenetrable Secret Protection (CIS Benchmark 4.10):
- NEVER embed credentials, `.env` files, or private keys in `ARG` or `ENV` layers.
- Build-time secrets must use BuildKit mounts: `RUN --mount=type=secret,id=npm_token NPM_TOKEN=$(cat /run/secrets/npm_token) npm ci`.
- A strict `.dockerignore` is MANDATORY (`.git`, `.env*`, `*.pem`, `*.key`, `id_rsa*`, `node_modules`).

### 4. Volatility Caching Hierarchy:
- Order instructions from slowest-changing to fastest-changing: Base image -> System dependencies -> Package manifests (`package.json`, `go.mod`) -> Frozen lockfile install (`npm ci`) -> Source code copy -> Build.

### 5. Deterministic Healthcheck Directives (CIS Benchmark 4.6):
- Every production Dockerfile must include an explicit `HEALTHCHECK`:
  `HEALTHCHECK --interval=30s --timeout=5s --start-period=5s --retries=3 CMD <health-probe>`
- In Distroless, use a lightweight compiled binary or native runtime check (`node -e "..."`).
</DOCKER_HARDENING_DOCTRINE>
