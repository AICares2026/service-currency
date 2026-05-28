## Stack
- C++ (primary language, ~5% of files tracked)
- Docker (containerisation tooling)
- No external package manager detected (no go.mod, requirements.txt, package.json found)

## Constraints
Never modify:
- `*.lock` files of any kind
- Any file named `credentials`, `.env`, `secrets.*`, or containing API keys/tokens
- Generated code files (identifiable by headers like `// DO NOT EDIT` or `// generated`)
- Migration files (any `migrations/` directory or files matching `*_migration.*`)
- `docker-compose.override.yml` if present (environment-specific overrides)

## Conventions
- Repository name: `service-currency` — this is a microservice; changes must preserve service boundaries
- C++ files: follow existing naming and formatting in the repo; do not introduce new build systems without confirming existing one
- Dockerfiles: located at repo root or in subdirectories; harden without changing exposed ports or base image names unless a CVE requires it
- CVE scan agent has shown 0 files changed across all runs with version `d6cc81e5` — do not alter CVE scan tooling config
- No test directory detected; do not create one speculatively

## Dependency manifests
- No canonical manifest detected; check for `CMakeLists.txt`, `Makefile`, or `conanfile.txt` before assuming build dependencies
- Dockerfile `FROM` lines are the primary versioned dependency surface — update tags only with verified, published image digests
