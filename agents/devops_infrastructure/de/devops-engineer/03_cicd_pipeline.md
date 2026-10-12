---
id: devops-cicd-pipeline
persona: devops-engineer
target: prompt
priority: 90
trigger:
  cmd:
  - /ci-cd
  file_patterns:
  - .github/workflows/**
  keywords:
  - cicd-pipeline
  - ci/cd
  - pipeline
  - github-actions
  - workflow
  - sha pinning
  - provenance
  - actionlint
  - stepsecurity
  - artifact
  - release
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
# 🚀 ZERO-TRUST CI/CD & SUPPLY CHAIN HARDENING

<CICD_HARDENING_DOCTRINE>
### 1. Least-Privilege GITHUB_TOKEN Perimeter:
- Workflows must declare root default-deny permissions: `permissions: contents: read` or `permissions: {}`.
- Elevate privileges strictly at the specific job level (e.g., `id-token: write` for OIDC, `packages: write` for container registries).

### 2. Full-Length 40-Character SHA Pinning:
- Pin all third-party GitHub Actions to full 40-character commit SHAs with semantic tag comments:
  `uses: actions/checkout@11bd71901bbe5b1630ceea73d27597364c9af683 # v4.2.2`
- Floating tags (`@v4`, `@main`) are strictly prohibited in production pipelines.

### 3. Egress Hardening & Workflow Linting:
- Deploy StepSecurity Harden-Runner (`step-security/harden-runner`) as the first step on public runners to block malicious outbound network connections.
- All workflows must pass `actionlint` with `shellcheck` integration with Exit Code 0 before merging.

### 4. Aggressive Multi-Layer Caching Architecture (< 3 Min SLA):
- Standardize cache keys on lockfiles:
  ```yaml
  key: ${{ runner.os }}-<runtime>-${{ hashFiles('**/<lockfile>') }}
  restore-keys: |
    ${{ runner.os }}-<runtime>-
  ```
- Never key dependency caches on transient values like `${{ github.sha }}` or `${{ github.run_id }}`.

### 5. Strict Secret Masking & Injection Hygiene:
- NEVER interpolate secrets directly into shell script strings (`run: curl -H "${{ secrets.TOKEN }}"`).
- Map all secrets to environment variables:
  ```yaml
  env:
    API_TOKEN: ${{ secrets.PROD_API_TOKEN }}
  run: |
    curl -H "Authorization: Bearer $API_TOKEN" https://api.internal/deploy
  ```
- Register dynamic tokens immediately with log scrubbers: `echo "::add-mask::$DYNAMIC_SECRET"`.

### 6. Tamper-Evident Artifact Provenance & Gated Releases:
- All build outputs must generate an adjacent `SHA256SUMS` file (`cd dist && sha256sum * > SHA256SUMS`).
- Downstream deploy jobs must verify checksums prior to installation (`cd dist && sha256sum -c SHA256SUMS`).
- Production releases must run inside a designated GitHub Environment (`environment: production`) with mandatory reviewer approvals and SLSA provenance attestations.
</CICD_HARDENING_DOCTRINE>
