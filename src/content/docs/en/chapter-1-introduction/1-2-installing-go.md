---
title: Installing Go
sidebar:
  order: 2
  label: 1.2 Installing Go
---

## Context

To start programming in Go, you need to install the Go toolchain (compiler, standard library, and command‑line tools). Go supports Linux, macOS, Windows, and several other platforms.

## Installation steps per operating system

### Linux

1. Download the latest tarball from [go.dev/dl](https://go.dev/dl/), e.g., `go1.24.0.linux-amd64.tar.gz`.
2. Remove any previous Go installation (usually `/usr/local/go`):
   ```bash
   sudo rm -rf /usr/local/go
   ```
3. Extract the tarball into `/usr/local`:
   ```bash
   sudo tar -C /usr/local -xzf go1.24.0.linux-amd64.tar.gz
   ```
4. Add `/usr/local/go/bin` to your `PATH` environment variable (add to `~/.profile` or `~/.bashrc`):
   ```bash
   export PATH=$PATH:/usr/local/go/bin
   ```

### macOS

- Using the official installer: download the `.pkg` file from [go.dev/dl](https://go.dev/dl/) and run it.
- Using Homebrew: `brew install go`.

### Windows

- Download the MSI installer from [go.dev/dl](https://go.dev/dl/) and run it. It will automatically set up the `PATH` environment variable.

## Verify the installation

After installation, open a new terminal and run:

## Code example

```bash
go version
```

## Output

```
go version go1.24.0 linux/amd64
```

## Additional verification

Check the Go environment:

```bash
go env
```

This shows variables like `GOROOT` (installation path), `GOPATH` (legacy workspace, not needed with modules), and `GOOS`/`GOARCH`.

## Useful links

- [Download Go](https://go.dev/dl/)
- [Official installation instructions](https://go.dev/doc/install)
- [Setting up Go for Windows](https://go.dev/doc/install/windows)
