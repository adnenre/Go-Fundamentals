---
title: Type conversions
sidebar:
  order: 6
  label: 2.6 Type conversions
---

## Context

Go does **not** have implicit type conversions. You must explicitly convert values using `T(v)`, where `T` is the target type and `v` is the value.

## Example

Convert between different numeric types and between string and byte slice.

## Code example

```go
package main

import "fmt"

func main() {
    var a int = 42
    var b float64 = float64(a)
    var c uint = uint(a)

    fmt.Println(a, b, c)

    // String to byte slice
    s := "hello"
    bs := []byte(s)
    fmt.Println(bs)

    // Byte slice to string
    s2 := string(bs)
    fmt.Println(s2)
}
```

## Output

```bash
42 42 42
[104 101 108 108 111]
hello
```

## Useful links

- [Go specification: Conversions](https://go.dev/ref/spec#Conversions)
- [Go by Example: Type Conversions](https://gobyexample.com/type-conversions)
