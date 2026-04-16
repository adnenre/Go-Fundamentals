---
title: Analyse de nombres (Number parsing)
sidebar:
  order: 7
  label: 2.7 Analyse de nombres (Number parsing)
---

## Contexte

Convertir des chaînes en nombres en utilisant le package `strconv`. Les fonctions les plus courantes :

- `strconv.Atoi(s)` – chaîne vers `int` (base 10)
- `strconv.ParseInt(s, base, bitSize)`
- `strconv.ParseFloat(s, bitSize)`
- `strconv.ParseUint(s, base, bitSize)`

## Exemple

Analyser un entier et un nombre flottant à partir de chaînes.

## Code exemple

```go
package main

import (
    "fmt"
    "strconv"
)

func main() {
    s1 := "123"
    i, err := strconv.Atoi(s1)
    if err == nil {
        fmt.Println("Entier analysé :", i)
    }

    s2 := "3.14159"
    f, err := strconv.ParseFloat(s2, 64)
    if err == nil {
        fmt.Println("Flottant analysé :", f)
    }

    // Hexadécimal
    hex := "FF"
    val, _ := strconv.ParseInt(hex, 16, 64)
    fmt.Printf("Hex %s = %d\n", hex, val)
}
```

## Sortie

```bash
Entier analysé : 123
Flottant analysé : 3.14159
Hex FF = 255
```

## Liens utiles

- [Documentation du package strconv](https://pkg.go.dev/strconv)
- [Go by Example : Analyse de nombres](https://gobyexample.com/fr/number-parsing)
