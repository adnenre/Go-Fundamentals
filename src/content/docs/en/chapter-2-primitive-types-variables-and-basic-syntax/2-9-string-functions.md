---
title: String functions
sidebar:
  order: 9
  label: 2.9 String functions
---

## Context

The `strings` package provides many utility functions for string manipulation.

Common functions: `Contains`, `Count`, `HasPrefix`, `HasSuffix`, `Index`, `Join`, `Repeat`, `Replace`, `Split`, `ToLower`, `ToUpper`, `TrimSpace`.

## Example

Use several string functions.

## Code example

```go
package main

import (
    "fmt"
    "strings"
)

func main() {
    s := "  Hello, Go!  "
    fmt.Println("Trimmed:", strings.TrimSpace(s))
    fmt.Println("Upper:", strings.ToUpper(s))
    fmt.Println("Contains 'Go':", strings.Contains(s, "Go"))
    fmt.Println("Split by space:", strings.Split(s, " "))
    fmt.Println("Replace Go with Gophers:", strings.ReplaceAll(s, "Go", "Gophers"))
    fmt.Println("Join:", strings.Join([]string{"a", "b", "c"}, "-"))
}
```

## Output

```bash
Trimmed: Hello, Go!
Upper:   HELLO, GO!
Contains 'Go': true
Split by space: [  Hello,  Go!  ]
Replace Go with Gophers:   Hello, Gophers!
Join: a-b-c
```

## Useful links

- [strings package documentation](https://pkg.go.dev/strings)
- [Go by Example: String Functions](https://gobyexample.com/string-functions)
