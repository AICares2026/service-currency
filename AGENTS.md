## Stack
C++ (primary language), Docker (containerization). No external C++ package manager detected.

## Constraints
Never modify:
- Any lock files or auto-generated files
- Credential or secret files (`.env`, `*.key`, `*.pem`, `*.secret`)
- Migration files or schema definitions
- `CMakeCache.txt`, `CMakeFiles/` (generated CMake artefacts)
- `.git/` directory

## Conventions
- C++ source files expected to follow existing naming patterns in the repo
- Docker image hardening: use non-root USER, drop capabilities, pin base image digests, avoid `latest` tags
- C++ modernization targets C++17 or later; prefer `auto`, range-for, `nullptr`, scoped enums, RAII
- Do not introduce new dependencies without updating the relevant manifest

## Dependency manifests
- `Dockerfile` (base image and any `apt` package versions)
- Any `CMakeLists.txt` files (library version requirements)
