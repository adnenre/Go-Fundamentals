---
title: Project layout
sidebar:
  order: 4
  label: 1.4 Project layout
---

## Context

Unlike many languages, Go does **not** enforce a rigid project structure. However, the community has adopted conventions that work well for small and large projects alike. The most important rule: keep it simple.

## Minimal structure (for a single executable)

```
myproject/
├── go.mod
├── go.sum
└── main.go
```

## Recommended structure for larger projects

```
myproject/
├── cmd/
│   ├── myapp/          # main package for the application
│   │   └── main.go
│   └── othertool/      # another executable
│       └── main.go
├── internal/           # private packages (not importable by other modules)
│   └── myhelper/
│       └── helper.go
├── pkg/                # public packages that other modules can import
│   └── mylib/
│       └── lib.go
├── api/                # API definitions (OpenAPI, gRPC proto, etc.)
├── web/                # web assets (templates, static files)
├── scripts/            # build scripts, etc.
├── test/               # external test files
├── go.mod
└── go.sum
```

## Explanation of key folders

- `cmd/` – Contains executable commands. Each subdirectory is a separate `main` package.
- `internal/` – Code that is **private** to this module. No other module can import it.
- `pkg/` – Code that is **public** and intended to be used by other modules.
- `api/` – API contract files (e.g., Protocol Buffers, OpenAPI specs).
- `web/` – Static web files, templates, etc.

## Example

A minimal CLI tool layout.

## Code example

```bash
mycli/
├── go.mod
├── main.go
```

## Useful links

- [Organizing a Go module (official)](https://go.dev/doc/modules/layout)
- [Standard Go Project Layout (community)](https://github.com/golang-standards/project-layout)
