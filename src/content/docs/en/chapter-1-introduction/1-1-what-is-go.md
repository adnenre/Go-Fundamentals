---
title: What is Go
sidebar:
  order: 1
  label: 1.1 What is Go
---

## Context

Go (also called Golang) is an open‑source programming language created at Google in 2007 by Robert Griesemer, Rob Pike, and Ken Thompson. It was publicly announced in November 2009, and the first stable version, Go 1.0, was released in March 2012.

Go was designed to address common criticisms of other languages (slow compilation, cumbersome concurrency, complex dependency management) while keeping their strengths. Its key design goals are:

- **Simplicity** – Minimal syntax, no classes or inheritance, no exceptions, no generics until 2022 (and they are kept simple).
- **Efficiency** – Compiled to native code, fast execution, low memory footprint, and fast compilation times.
- **Built‑in concurrency** – Goroutines and channels make concurrent programming safe and easy.

Go is a **statically typed**, **compiled** language with **garbage collection**. It has become the language of the cloud, powering tools like Docker, Kubernetes, Terraform, and many others.

## Version History and Key Features

Go follows a six‑month release cycle (every February and August). Each version is supported until two newer versions are released.

- **Go 1.0 (2012-03-28)** – First stable release, compatibility guarantee.
- **Go 1.1 (2013-05-13)** – Performance improvements, race detector.
- **Go 1.2 (2013-12-01)** – Configurable thread limit, better scheduler.
- **Go 1.3 (2014-06-18)** – Improved stack management.
- **Go 1.4 (2014-12-10)** – Android support, `go generate`.
- **Go 1.5 (2015-08-19)** – Compiler and runtime rewritten in Go, new GC.
- **Go 1.6 (2016-02-17)** – HTTP/2 support, GC improvements.
- **Go 1.7 (2016-08-15)** – `context` package introduced.
- **Go 1.8 (2017-02-16)** – Sub‑millisecond GC pauses, graceful shutdown.
- **Go 1.9 (2017-08-24)** – Type aliases.
- **Go 1.10 (2018-02-16)** – Test caching, automatic package caching.
- **Go 1.11 (2018-08-24)** – **Go Modules** (dependency management), WebAssembly.
- **Go 1.12 (2019-02-25)** – Go Modules improvements, TLS 1.3.
- **Go 1.13 (2019-09-03)** – Error wrapping, improved number literals.
- **Go 1.14 (2020-02-25)** – Go Modules production‑ready, `defer` performance.
- **Go 1.15 (2020-08-11)** – Linker improvements (20% faster).
- **Go 1.16 (2021-02-16)** – `embed` package, Go Modules default.
- **Go 1.17 (2021-08-16)** – Register‑based calling convention (~5% faster).
- **Go 1.18 (2022-03-15)** – **Generics** (type parameters).
- **Go 1.19 (2022-08-02)** – Generics refinements, doc comments.
- **Go 1.20 (2023-02-01)** – Profile‑Guided Optimization (PGO), slice to array conversions.
- **Go 1.21 (2023-08-08)** – `min`, `max`, `clear` built‑ins, PGO generally available.
- **Go 1.22 (2024-02-06)** – Loop variable capture fix (per‑iteration scope), enhanced routing, range‑over‑function iterators preview.
- **Go 1.23 (2024-08)** – Further refinements and performance.
- **Go 1.24 (2025-02)** – Latest stable release (at the time of writing). See release notes for details.

## Example

A minimal Go program consists of a `package main` declaration and a `func main()` function.

## Code example

```go
package main

import "fmt"

func main() {
    fmt.Println("Hello, Go!")
}
```

## Output

```
Hello, Go!
```

## Useful links

- [Official Go website](https://go.dev/)
- [Official Go release history](https://go.dev/doc/devel/release)
- [Go History (The Go Blog)](https://go.dev/blog/11year)
- [Go FAQ](https://go.dev/doc/faq)
