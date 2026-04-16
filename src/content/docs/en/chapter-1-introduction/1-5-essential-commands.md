---
title: Essential commands
sidebar:
  order: 5
  label: 1.5 Essential commands
---

## Context

The `go` command is the primary interface to the Go toolchain. Here are the most important subcommands used daily.

## Subcommands in detail

### `go run`

Compiles and runs a Go program in one step. The compiled binary is placed in a temporary directory and deleted after execution.

```bash
go run main.go
```

You can pass arguments to the program after a `--` separator:

```bash
go run main.go -- arg1 arg2
```

### `go build`

Compiles the current package and its dependencies. For a `main` package, it produces an executable binary. For a non‑main package, it compiles and discards the result (useful for checking errors).

```bash
# Build executable (name = directory name)
go build

# Build with custom output name
go build -o myapp

# Build for a different operating system
GOOS=windows GOARCH=amd64 go build
```

### `go test`

Runs tests defined in `*_test.go` files. It discovers functions named `TestXxx(t *testing.T)` and runs them.

```bash
# Run all tests in current directory
go test

# Verbose output
go test -v

# Run specific test function
go test -run=TestAdd

# Run tests with coverage
go test -cover

# Run benchmarks
go test -bench=.
```

### `go fmt`

Formats Go source files according to the official style (no tabs, consistent indentation). This command rewrites files in place. It is safe to run on any Go code.

```bash
# Format current directory
go fmt

# Format all packages in the module
go fmt ./...
```

### `go vet`

Reports suspicious constructs that are likely bugs, such as unreachable code, incorrect format strings, or race conditions (when run with `-race`). It does not produce false positives in most cases.

```bash
go vet
go vet ./...
```

### `go mod tidy`

Cleans up the `go.mod` and `go.sum` files by adding missing requirements and removing unused ones. Always run this before committing changes to a module.

```bash
go mod tidy
```

## Example

Compile and run a simple program.

## Code example

```bash
go run main.go
```

## Output

```bash
Hello, Go!
```

## Useful links

- [Go command documentation](https://go.dev/doc/cmd)
- [How to write Go code](https://go.dev/doc/code)
