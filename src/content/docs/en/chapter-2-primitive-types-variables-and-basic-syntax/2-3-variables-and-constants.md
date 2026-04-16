---
title: Variables and constants
sidebar:
  order: 3
  label: 2.3 Variables and constants
---

## Context

Go provides several ways to declare variables and constants.

### Variable declarations

1. **`var` with type** – `var name string`
2. **`var` with initializer** – `var name = "Alice"` (type inferred)
3. **Short assignment `:=`** – `name := "Alice"` (inside functions only)
4. **Multiple variables** – `var x, y int = 1, 2` or `x, y := 1, 2`

### Constants

- Declared with `const` keyword.
- Cannot be changed after declaration.
- Can be untyped (e.g., `const Pi = 3.14`).

## Example

Demonstrate different variable declarations and constants.

## Code example

```go
package main

import "fmt"

const Pi = 3.14159
const (
    StatusOK = 200
    StatusNotFound = 404
)

func main() {
    var name string = "Alice"
    var age = 30
    city := "Paris"
    var x, y int = 10, 20
    a, b := "hello", true

    fmt.Println(name, age, city)
    fmt.Println(x, y, a, b)
    fmt.Println(Pi, StatusOK, StatusNotFound)
}
```

## Output

```bash
Alice 30 Paris
10 20 hello true
3.14159 200 404
```

## Useful links

- [Go specification: Variables](https://go.dev/ref/spec#Variables)
- [Go by Example: Variables](https://gobyexample.com/variables)
- [Go by Example: Constants](https://gobyexample.com/constants)
