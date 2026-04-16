---
title: Built-in types
sidebar:
  order: 1
  label: 2.1 Built-in types
---

## Context

Go is a statically typed language. Every variable has a type known at compile time. Here are the main built‑in types.

### Boolean type

- `bool` – `true` or `false`

### Numeric types

- **Signed integers**: `int8`, `int16`, `int32`, `int64`, `int` (platform‑dependent: 32 or 64 bits)
- **Unsigned integers**: `uint8`, `uint16`, `uint32`, `uint64`, `uint`, `uintptr`
- **Floating point**: `float32`, `float64`
- **Complex numbers**: `complex64` (float32+float32), `complex128` (float64+float64)
- **Byte and rune**: `byte` = `uint8` (ASCII/UTF‑8 byte), `rune` = `int32` (Unicode code point)

### String type

- `string` – immutable sequence of bytes (usually UTF‑8)

## Example

Declaring variables with explicit types.

## Code example

```go
package main

import "fmt"

func main() {
    var flag bool = true
    var age int = 30
    var price float64 = 19.99
    var name string = "Alice"
    var letter byte = 'A'
    var symbol rune = 'é'

    fmt.Println(flag, age, price, name, letter, symbol)
}
```

## Output

```bash
true 30 19.99 Alice 65 233
```

## Useful links

- [Go language specification: Types](https://go.dev/ref/spec#Types)
- [Go by Example: Values](https://gobyexample.com/values)
