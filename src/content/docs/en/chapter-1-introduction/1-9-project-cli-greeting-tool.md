---
title: Project CLI Greeting Tool
sidebar:
  order: 9
  label: 1.9 Project CLI Greeting Tool
---

## Context

This project combines several basic concepts: reading user input (using `bufio`), handling strings (`strings.TrimSpace`), and printing formatted output.

The program will:

1. Ask for the user's name.
2. Ask for their favourite colour.
3. Print a personalised greeting.

## Detailed explanation of used packages

- `bufio` – Provides buffered I/O, which is efficient for reading whole lines.
- `os.Stdin` – Standard input (the terminal).
- `strings.TrimSpace` – Removes leading/trailing whitespace and newlines.
- `fmt.Printf` – Formatted printing with `%s` for strings and `\n` for newline.

## Step‑by‑step code

```go
package main

import (
    "bufio"
    "fmt"
    "os"
    "strings"
)

func main() {
    // Create a buffered reader from standard input
    reader := bufio.NewReader(os.Stdin)

    // Prompt for name
    fmt.Print("Enter your name: ")
    name, err := reader.ReadString('\n')
    if err != nil {
        fmt.Println("Error reading input:", err)
        return
    }
    name = strings.TrimSpace(name) // remove newline and spaces

    // Prompt for colour
    fmt.Print("Enter your favourite colour: ")
    colour, err := reader.ReadString('\n')
    if err != nil {
        fmt.Println("Error reading input:", err)
        return
    }
    colour = strings.TrimSpace(colour)

    // Print greeting
    fmt.Printf("\nHello %s! Your favourite colour %s is awesome!\n", name, colour)
}
```

## Example interaction

```bash
Enter your name: Alice
Enter your favourite colour: blue

Hello Alice! Your favourite colour blue is awesome!
```

## Error handling

If the user presses Ctrl+D (EOF) or an error occurs, the program prints an error and exits gracefully.

## Extensions (optional)

- Add colour using ANSI escape codes.
- Validate that the colour is not empty.
- Use a loop to ask again if input is invalid.

## Useful links

- [bufio package documentation](https://pkg.go.dev/bufio)
- [strings package documentation](https://pkg.go.dev/strings)
- [fmt package documentation](https://pkg.go.dev/fmt)
- [Go by Example: Command-Line Arguments](https://gobyexample.com/command-line-arguments)
