---
title: Chaînes et runes
sidebar:
  order: 8
  label: 2.8 Chaînes et runes
---

## Contexte

En Go, une `string` est une slice d'octets en lecture seule. Elle peut contenir des octets arbitraires, mais contient généralement du texte encodé en UTF‑8.

Une `rune` est un `int32` représentant un point de code Unicode. Elle est utilisée pour manipuler des caractères qui peuvent occuper plus d'un octet (ex. é, 世).

## Exemple

Itérer sur une chaîne par octets vs par runes.

## Code exemple

```go
package main

import "fmt"

func main() {
    s := "Bonjour, 世界"

    fmt.Println("Octets :")
    for i := 0; i < len(s); i++ {
        fmt.Printf("%x ", s[i])
    }
    fmt.Println()

    fmt.Println("Runes :")
    for i, r := range s {
        fmt.Printf("%d: %c (%U)\n", i, r, r)
    }
}
```

## Sortie

```bash
Octets :
42 6f 6e 6a 6f 75 72 2c 20 e4 b8 96 e7 95 8c
Runes :
0: B (U+0042)
1: o (U+006F)
2: n (U+006E)
3: j (U+006A)
4: o (U+006F)
5: u (U+0075)
6: r (U+0072)
7: , (U+002C)
8:   (U+0020)
9: 世 (U+4E16)
12: 界 (U+754C)
```

## Liens utiles

- [Chaînes, octets, runes et caractères en Go](https://go.dev/blog/strings)
- [Go by Example : Chaînes et runes](https://gobyexample.com/fr/strings-and-runes)
