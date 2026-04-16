---
title: Basic I O
sidebar:
  order: 5
  label: 2.5 Basic I O
---

## Context

Go provides several ways to read input and write output. The most common are:

- **Output**: `fmt.Print`, `fmt.Println`, `fmt.Printf`
- **Input**: `fmt.Scan`, `fmt.Scanln`, `fmt.Scanf`, and `bufio` for full lines.

## Example

Read a name and age from the user, then print a greeting.

## Code example

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

    fmt.Print("Enter your name: ")
    name, _ := reader.ReadString('\n')
    name = strings.TrimSpace(name)

    fmt.Print("Enter your age: ")
    ageStr, _ := reader.ReadString('\n')
    age, _ := strconv.Atoi(strings.TrimSpace(ageStr))

    fmt.Printf("Hello %s, you are %d years old.\n", name, age)
}
```

## Example interaction

```bash
Enter your name: Alice
Enter your age: 30
Hello Alice, you are 30 years old.
```

## Useful links

- [fmt package documentation](https://pkg.go.dev/fmt)
- [bufio package documentation](https://pkg.go.dev/bufio)
