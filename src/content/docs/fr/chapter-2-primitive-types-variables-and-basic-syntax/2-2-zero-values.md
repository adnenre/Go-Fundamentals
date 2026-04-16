---
title: Valeurs zéro
sidebar:
  order: 2
  label: 2.2 Valeurs zéro
---

## Contexte

En Go, les variables déclarées sans valeur initiale explicite reçoivent automatiquement une **valeur zéro**. C'est la valeur par défaut pour chaque type.

| Type                                                   | Valeur zéro        |
| ------------------------------------------------------ | ------------------ |
| `bool`                                                 | `false`            |
| numérique (`int`, `float`, etc.)                       | `0`                |
| `string`                                               | `""` (chaîne vide) |
| pointeurs, slices, maps, canaux, fonctions, interfaces | `nil`              |

## Exemple

Déclarez des variables sans initialisation et affichez leurs valeurs zéro.

## Code exemple

```go
package main

import "fmt"

func main() {
    var a bool
    var b int
    var c float64
    var d string
    var e []int
    var f map[string]int

    fmt.Printf("bool: %v\n", a)
    fmt.Printf("int: %v\n", b)
    fmt.Printf("float64: %v\n", c)
    fmt.Printf("string: %q\n", d)
    fmt.Printf("slice: %v\n", e)
    fmt.Printf("map: %v\n", f)
}
```

## Sortie

```bash
bool: false
int: 0
float64: 0
string: ""
slice: []
map: map[]
```

## Liens utiles

- [Spécification Go : Valeur zéro](https://go.dev/ref/spec#The_zero_value)
- [Go by Example : Valeurs zéro](https://gobyexample.com/fr/zero-values)
