---
title: Project Simple Calculator
sidebar:
  order: 12
  label: 2.12 Project Simple Calculator
---

## Context

Build a command‑line calculator that reads two numbers and an operator (`+`, `-`, `*`, `/`), then prints the result.

This project combines:

- Reading user input (`bufio`, `fmt.Scanln`)
- Type conversion (`strconv.ParseFloat`)
- Conditional logic (`switch`)
- Error handling

## Step‑by‑step code

```go
package main

import (
    "bufio"
    "fmt"
    "os"
    "strconv"
    "strings"
)

func main() {
    reader := bufio.NewReader(os.Stdin)

    // Read first number
    fmt.Print("Enter first number: ")
    num1Str, _ := reader.ReadString('\n')
    num1, err1 := strconv.ParseFloat(strings.TrimSpace(num1Str), 64)
    if err1 != nil {
        fmt.Println("Invalid number")
        return
    }

    // Read operator
    fmt.Print("Enter operator (+, -, *, /): ")
    op, _ := reader.ReadString('\n')
    op = strings.TrimSpace(op)

    // Read second number
    fmt.Print("Enter second number: ")
    num2Str, _ := reader.ReadString('\n')
    num2, err2 := strconv.ParseFloat(strings.TrimSpace(num2Str), 64)
    if err2 != nil {
        fmt.Println("Invalid number")
        return
    }

    // Perform calculation
    var result float64
    switch op {
    case "+":
        result = num1 + num2
    case "-":
        result = num1 - num2
    case "*":
        result = num1 * num2
    case "/":
        if num2 == 0 {
            fmt.Println("Error: division by zero")
            return
        }
        result = num1 / num2
    default:
        fmt.Println("Invalid operator")
        return
    }

    fmt.Printf("%g %s %g = %g\n", num1, op, num2, result)
}
```

## Example interaction

```bash
Enter first number: 10
Enter operator (+, -, *, /): /
Enter second number: 3
10 / 3 = 3.3333333333333335
```

## Another example (division by zero)

```bash
Enter first number: 5
Enter operator (+, -, *, /): /
Enter second number: 0
Error: division by zero
```

## Useful links

- [strconv package](https://pkg.go.dev/strconv)
- [bufio package](https://pkg.go.dev/bufio)
- [fmt package](https://pkg.go.dev/fmt)
