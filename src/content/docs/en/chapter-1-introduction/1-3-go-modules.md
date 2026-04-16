---
title: Go modules
sidebar:
  order: 3
  label: 1.3 Go modules
---

## Context

A **Go module** is a collection of related Go packages versioned together as a single unit. Modules replace the old `GOPATH`‑based workflow and provide:

- **Versioning** – Semantic versions (v1.2.3) are enforced.
- **Dependency management** – `go.mod` lists required modules and versions.
- **Reproducible builds** – `go.sum` ensures integrity.

The module system was introduced in Go 1.11 and became the default in Go 1.16.

## Core files

- `go.mod` – Defines the module path (e.g., `github.com/user/project`) and its dependencies.
- `go.sum` – Contains checksums of dependencies to verify integrity.

## Basic commands

| Command                | Purpose                                             |
| ---------------------- | --------------------------------------------------- |
| `go mod init <module>` | Create a new module in the current directory.       |
| `go get <module>`      | Add a dependency (or update it).                    |
| `go mod tidy`          | Remove unused dependencies and add missing ones.    |
| `go mod vendor`        | Copy dependencies to a `vendor/` folder (optional). |

## Example

Create a new module named "hello".

## Code example

```bash
mkdir myproject
cd myproject
go mod init hello
```

## Output

```
go: creating new go.mod: module hello
```

Now `go.mod` contains:

```
module hello

go 1.24
```

## Adding a dependency

```bash
go get rsc.io/quote
```

This updates `go.mod` and downloads the module.

## Useful links

- [Using Go Modules (official)](https://go.dev/doc/modules/managing-dependencies)
- [Go Modules Reference](https://go.dev/ref/mod)
- [Blog: Using Go Modules](https://go.dev/blog/using-go-modules)
