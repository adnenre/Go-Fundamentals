---
title: Conversions de types
sidebar:
  order: 6
  label: 2.6 Conversions de types
---

## Contexte

Go n'a **pas** de conversions de types implicites. Vous devez convertir explicitement les valeurs en utilisant `T(v)`, où `T` est le type cible et `v` la valeur.

## Exemple

Convertir entre différents types numériques et entre chaîne et slice d'octets.

## Code exemple

```go
package main

import "fmt"

func main() {
    var a int = 42
    var b float64 = float64(a)
    var c uint = uint(a)

    fmt.Println(a, b, c)

    // Chaîne vers slice d'octets
    s := "bonjour"
    bs := []byte(s)
    fmt.Println(bs)

    // Slice d'octets vers chaîne
    s2 := string(bs)
    fmt.Println(s2)
}
```

## Sortie

```bash
42 42 42
[98 111 110 106 111 117 114]
bonjour
```

## Liens utiles

- [Spécification Go : Conversions](https://go.dev/ref/spec#Conversions)
- [Go by Example : Conversions de types](https://gobyexample.com/fr/type-conversions)
