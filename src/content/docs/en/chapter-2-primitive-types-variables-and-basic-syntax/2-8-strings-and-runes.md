---
title: Strings and runes
sidebar:
  order: 8
  label: 2.8 Strings and runes
---

## Context

In Go, a `string` is a read‑only slice of bytes. It can contain arbitrary bytes, but typically holds UTF‑8 encoded text.

A `rune` is an `int32` representing a Unicode code point. It is used to handle characters that may be more than one byte long (e.g., é, 世).

## Example

Iterate over a string by bytes vs by runes.

## Code example

```go
package main

import "fmt"

func main() {
    s := "Hello, 世界"

    fmt.Println("Bytes:")
    for i := 0; i < len(s); i++ {
        fmt.Printf("%x ", s[i])
    }
    fmt.Println()

    fmt.Println("Runes:")
    for i, r := range s {
        fmt.Printf("%d: %c (%U)\n", i, r, r)
    }
}
```

## Output

```bash
Bytes:
48 65 6c 6c 6f 2c 20 e4 b8 96 e7 95 8c
Runes:
0: H (U+0048)
1: e (U+0065)
2: l (U+006C)
3: l (U+006C)
4: o (U+006F)
5: , (U+002C)
6:   (U+0020)
7: 世 (U+4E16)
10: 界 (U+754C)
```

## Useful links

- [Strings, bytes, runes and characters in Go](https://go.dev/blog/strings)
- [Go by Example: Strings and Runes](https://gobyexample.com/strings-and-runes)
