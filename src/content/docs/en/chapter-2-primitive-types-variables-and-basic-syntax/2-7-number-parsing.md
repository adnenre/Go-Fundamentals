---
title: Number parsing
sidebar:
  order: 7
  label: 2.7 Number parsing
---

## Context

Convert strings to numbers using the `strconv` package. The most common functions:

- `strconv.Atoi(s)` – string to `int` (base 10)
- `strconv.ParseInt(s, base, bitSize)`
- `strconv.ParseFloat(s, bitSize)`
- `strconv.ParseUint(s, base, bitSize)`

## Example

Parse an integer and a floating point number from strings.

## Code example

```go
package main

import (
    "fmt"
    "strconv"
)

func main() {
    s1 := "123"
    i, err := strconv.Atoi(s1)
    if err == nil {
        fmt.Println("Parsed int:", i)
    }

    s2 := "3.14159"
    f, err := strconv.ParseFloat(s2, 64)
    if err == nil {
        fmt.Println("Parsed float:", f)
    }

    // Hexadecimal
    hex := "FF"
    val, _ := strconv.ParseInt(hex, 16, 64)
    fmt.Printf("Hex %s = %d\n", hex, val)
}
```

## Output

```bash
Parsed int: 123
Parsed float: 3.14159
Hex FF = 255
```

## Useful links

- [strconv package documentation](https://pkg.go.dev/strconv)
- [Go by Example: Number Parsing](https://gobyexample.com/number-parsing)
