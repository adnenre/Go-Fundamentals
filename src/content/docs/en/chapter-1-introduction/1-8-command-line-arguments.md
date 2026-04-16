---
title: Command line arguments
sidebar:
  order: 8
  label: 1.8 Command line arguments
---

## Context

When you run a program from the terminal, you can pass arguments. In Go, these are available via `os.Args` – a slice of strings where `os.Args[0]` is the program name, and `os.Args[1:]` are the arguments.

For more complex flag parsing (e.g., `-port 8080`), the `flag` package provides a standard solution.

## Using `os.Args`

```go
package main

import (
    "fmt"
    "os"
)

func main() {
    // Print all arguments including program name
    for i, arg := range os.Args {
        fmt.Printf("args[%d] = %s\n", i, arg)
    }

    // Get positional arguments (skip program name)
    if len(os.Args) < 2 {
        fmt.Println("Please provide at least one argument")
        return
    }
    firstArg := os.Args[1]
    fmt.Println("First argument:", firstArg)
}
```

## Using the `flag` package

The `flag` package parses Unix‑style flags (e.g., `-name=value`, `--name value`).

```go
package main

import (
    "flag"
    "fmt"
)

func main() {
    var name string
    var age int
    flag.StringVar(&name, "name", "World", "name to greet")
    flag.IntVar(&age, "age", 0, "age of the person")
    flag.Parse()

    fmt.Printf("Hello, %s (age %d)\n", name, age)
    fmt.Println("Remaining args:", flag.Args())
}
```

Run with:

```bash
go run main.go -name Alice -age 30 extra1 extra2
```

## Output

```
Hello, Alice (age 30)
Remaining args: [extra1 extra2]
```

## Example

Print all received arguments.

## Code example

```go
package main

import (
    "fmt"
    "os"
)

func main() {
    fmt.Println("Arguments:", os.Args)
}
```

## Output (if run as `go run main.go hello world`)

```
Arguments: [/tmp/go-build123/b001/exe/main hello world]
```

## Useful links

- [os.Args documentation](https://pkg.go.dev/os#Args)
- [flag package documentation](https://pkg.go.dev/flag)
- [Command line arguments in Go (tutorial)](https://www.digitalocean.com/community/tutorials/command-line-arguments-in-go)
