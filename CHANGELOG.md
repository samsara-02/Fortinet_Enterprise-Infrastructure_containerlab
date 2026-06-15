# Changelog

All notable changes to this project will be documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.1.0/),
and this project adheres to [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

## [Unreleased]

### Added
- Project scaffolding and repository structure
- `README.md` with architecture overview, prerequisites, quick start, and project structure
- `.ansible-lint` configuration with production profile
- `.ansible-lint`, `.yamllint`, `.pre-commit-config.yaml` linting configuration
- `.githooks/commit-msg` and `.githooks/pre-commit` hooks enforcing Conventional Commits and linting
- `.github/workflows/lint.yml` CI pipeline (conventional commits, yamllint, ansible-lint, secret scan)
- `CLAUDE.md` with project guidance and containerlab conventions
- `CHANGELOG.md` in keepachangelog format
- `appliances/Fortinet/` directory structure with per-appliance `.sha256` checksums for FortiGate, FortiAnalyzer, FortiManager, FortiADC

### Changed
- Renamed `images/` to `appliances/` for clarity
- Updated `.gitignore` to reflect `appliances/` path for binary exclusions

[Unreleased]: https://github.com/samsara-02/Fortinet_Enterprise-Infrastructure_containerlab/compare/HEAD
