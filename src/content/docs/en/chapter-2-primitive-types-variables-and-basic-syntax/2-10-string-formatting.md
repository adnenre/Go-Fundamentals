---
title: String formatting
sidebar:
  order: 10
  label: 2.10 String formatting
---

## Context

The `fmt` package provides powerful string formatting with verbs similar to C's `printf`.

Common verbs:

- `%v` – default format
- `%+v` – struct with field names
- `%#v` – Go syntax representation
- `%T` – type
- `%d` – integer (decimal)
- `%f` – float
- `%s` – string
- `%q` – quoted string
- `%x` – hexadecimal
- `%p` – pointer

## Example

Format various data types.

## Code example

```go
package main

import "fmt"

type Person struct {
    Name string
    Age  int
}

func main() {
    p := Person{"Alice", 30}
    fmt.Printf("Default: %v\n", p)
    fmt.Printf("+v: %+v\n", p)
    fmt.Printf("#v: %#v\n", p)
    fmt.Printf("Type: %T\n", p)

    n := 42
    f := 3.14159
    s := "hello"

    fmt.Printf("Int: %d, Hex: %x, Bin: %b\n", n, n, n)
    fmt.Printf("Float: %.2f\n", f)
    fmt.Printf("String: %s, Quoted: %q\n", s, s)
}
```

## Output

```bash
Default: {Alice 30}
+v: {Name:Alice Age:30}
#v: main.Person{Name:"Alice", Age:30}
Type: main.Person
Int: 42, Hex: 2a, Bin: 101010
Float: 3.14
String: hello, Quoted: "hello"
```

## Useful links

- [fmt package documentation](https://pkg.go.dev/fmt)
- [Go by Example: String Formatting](https://gobyexample.com/string-formatting)
