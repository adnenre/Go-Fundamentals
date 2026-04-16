---
title: Environment variables
sidebar:
  order: 7
  label: 1.7 Environment variables
---

## Context

Environment variables are key‑value pairs that affect the behaviour of running processes. In Go, you can read them with `os.Getenv`, set them with `os.Setenv`, and delete them with `os.Unsetenv`.

## Important functions

| Function                | Description                                              |
| ----------------------- | -------------------------------------------------------- |
| `os.Getenv(key)`        | Returns the value as a string (empty string if not set). |
| `os.LookupEnv(key)`     | Returns `(value, true)` if set, otherwise `("", false)`. |
| `os.Setenv(key, value)` | Sets an environment variable.                            |
| `os.Unsetenv(key)`      | Deletes an environment variable.                         |
| `os.Environ()`          | Returns a slice of `"key=value"` strings.                |

## Example

Read the `HOME` directory (or `USERPROFILE` on Windows).

## Code example

```go
package main

import (
    "fmt"
    "os"
)

func main() {
    home := os.Getenv("HOME")
    if home == "" {
        home = os.Getenv("USERPROFILE") // Windows
    }
    fmt.Println("Home directory:", home)

    // Safer way
    if value, ok := os.LookupEnv("PATH"); ok {
        fmt.Println("PATH is set to:", value[:50]) // print first 50 chars
    }
}
```

## Output (example)

```bash
Home directory: /home/alice
PATH is set to: /usr/local/bin:/usr/bin:/bin
```

## Use case

Environment variables are ideal for configuration (e.g., database URLs, API keys) because they can be changed without recompiling the program.

## Useful links

- [os package documentation](https://pkg.go.dev/os#Getenv)
- [Environment variables in Go (tutorial)](https://go.dev/doc/tutorial/envvars)
