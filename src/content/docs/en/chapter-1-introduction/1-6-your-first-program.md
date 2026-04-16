---
title: Your first program
sidebar:
  order: 6
  label: 1.6 Your first program
---

## Context

Every Go program is composed of **packages**. A package named `main` is special: it defines an executable program. The entry point is a function named `main` with no parameters and no return values.

## Structure of a Go source file

```go
package main                     // Package declaration

import "fmt"                     // Import statement (standard library)

func main() {                    // Entry point function
    fmt.Println("Hello, World")  // Statement
}
```

## Explanation

- `package main` – Declares that this file belongs to the `main` package.
- `import "fmt"` – Imports the `fmt` package for formatted I/O.
- `func main()` – The program starts here. No arguments, no returns.
- `fmt.Println` – Prints a line to standard output.

## Running the program

Save the code as `main.go`, then in a terminal:

```bash
go run main.go
```

## Example

Create a file `main.go` with the content below.

## Code example

```go
package main

import "fmt"

func main() {
    fmt.Println("Hello, World")
}
```

## Output

```bash
Hello, World
```

## Useful links

- [Getting started with Go](https://go.dev/doc/tutorial/getting-started)
- [A Tour of Go](https://go.dev/tour/)
- [How to write Go code](https://go.dev/doc/code)
