---
title: Constants and iota enums
sidebar:
  order: 4
  label: 2.4 Constants and iota enums
---

## Context

`iota` is a predeclared identifier in Go that represents successive untyped integer constants. It is used to create enumerated constants (enums) easily.

- `iota` resets to `0` at the start of each `const` block.
- Within the block, each `const` line increments `iota` by 1.

## Example

Define days of the week and bit flags using `iota`.

## Code example

```go
package main

import "fmt"

const (
    Sunday = iota  // 0
    Monday         // 1
    Tuesday        // 2
    Wednesday      // 3
    Thursday       // 4
    Friday         // 5
    Saturday       // 6
)

const (
    Read = 1 << iota  // 1 << 0 = 1
    Write             // 1 << 1 = 2
    Exec              // 1 << 2 = 4
)

func main() {
    fmt.Println(Sunday, Monday, Tuesday)
    fmt.Println(Read, Write, Exec)
}
```

## Output

```bash
0 1 2
1 2 4
```

## Useful links

- [Go specification: Iota](https://go.dev/ref/spec#Iota)
- [Go by Example: Constants and iota](https://gobyexample.com/constants)
