---
title: Zero values
sidebar:
  order: 2
  label: 2.2 Zero values
---

## Context

In Go, variables declared without an explicit initial value are automatically assigned a **zero value**. This is the default value for each type.

| Type                                                    | Zero value          |
| ------------------------------------------------------- | ------------------- |
| `bool`                                                  | `false`             |
| numeric (`int`, `float`, etc.)                          | `0`                 |
| `string`                                                | `""` (empty string) |
| pointers, slices, maps, channels, functions, interfaces | `nil`               |

## Example

Declare variables without initialization and print their zero values.

## Code example

```go
package main

import "fmt"

func main() {
    var a bool
    var b int
    var c float64
    var d string
    var e []int
    var f map[string]int

    fmt.Printf("bool: %v\n", a)
    fmt.Printf("int: %v\n", b)
    fmt.Printf("float64: %v\n", c)
    fmt.Printf("string: %q\n", d)
    fmt.Printf("slice: %v\n", e)
    fmt.Printf("map: %v\n", f)
}
```

## Output

```bash
bool: false
int: 0
float64: 0
string: ""
slice: []
map: map[]
```

## Useful links

- [Go specification: Zero value](https://go.dev/ref/spec#The_zero_value)
- [Go by Example: Zero Values](https://gobyexample.com/zero-values)
