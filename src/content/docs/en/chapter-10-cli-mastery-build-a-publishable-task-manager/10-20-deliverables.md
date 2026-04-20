---
title: Deliverables
sidebar:
  order: 20
  label: 10.20 Deliverables
---

## Context

After completing the CLI Task Manager project, you should have a set of deliverables that make your tool production‑ready and publishable.

## Required deliverables

- **Source code** – All Go files with proper package structure, comments, and error handling.
- **Unit tests** – At least 80% coverage for core logic (loading, saving, adding tasks).
- **Documentation** – `README.md` with installation, usage, examples, and contribution guide.
- **Release binaries** – Pre‑compiled binaries for Linux, macOS, Windows (amd64, arm64) using GoReleaser.
- **Go module** – `go.mod` and `go.sum` with pinned dependencies.
- **Makefile** – Targets for `build`, `test`, `clean`, `install`, `release`.
- **CI/CD** – GitHub Actions (or similar) that runs tests and builds on push/tag.
- **Version tag** – Git tag (e.g., `v1.0.0`) for the release.

## Optional deliverables

- **Packaging** – Homebrew formula, Snap, or APT repository.
- **Shell completions** – Generate bash/zsh/fish completions with Cobra.
- **Colour output** – Respect `NO_COLOR` and `CLICOLOR`.
- **Progress bar** – For long operations (e.g., batch processing).

## Example README structure

# TaskMan – CLI Task Manager

## Installation

```bash
go install github.com/yourusername/taskman@latest
```

## Usage

```bash
taskman add "Buy milk"
taskman list
taskman complete 1
taskman delete 1
```

## Development

```bash
make test
make build
```

## License

MIT

## Useful links

- [GoReleaser Quick Start](https://goreleaser.com/quick-start/)
- [GitHub Actions for Go](https://docs.github.com/en/actions/automating-builds-and-tests/building-and-testing-go)
