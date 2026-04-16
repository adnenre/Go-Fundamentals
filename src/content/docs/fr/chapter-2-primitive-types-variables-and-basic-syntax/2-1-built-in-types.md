---
title: Types natifs
sidebar:
  order: 1
  label: 2.1 Types natifs
---

## Contexte

Go est un langage statiquement typé. Chaque variable a un type connu à la compilation. Voici les principaux types natifs.

### Type booléen

- `bool` – `true` (vrai) ou `false` (faux)

### Types numériques

- **Entiers signés** : `int8`, `int16`, `int32`, `int64`, `int` (dépend de la plateforme : 32 ou 64 bits)
- **Entiers non signés** : `uint8`, `uint16`, `uint32`, `uint64`, `uint`, `uintptr`
- **Flottants** : `float32`, `float64`
- **Nombres complexes** : `complex64` (float32+float32), `complex128` (float64+float64)
- **Octet et rune** : `byte` = `uint8` (octet ASCII/UTF‑8), `rune` = `int32` (point de code Unicode)

### Type chaîne

- `string` – séquence immuable d'octets (généralement UTF‑8)

## Exemple

Déclaration de variables avec types explicites.

## Code exemple

```go
package main

import "fmt"

func main() {
    var flag bool = true
    var age int = 30
    var prix float64 = 19.99
    var nom string = "Alice"
    var lettre byte = 'A'
    var symbole rune = 'é'

    fmt.Println(flag, age, prix, nom, lettre, symbole)
}
```

## Sortie

```bash
true 30 19.99 Alice 65 233
```

## Liens utiles

- [Spécification Go : Types](https://go.dev/ref/spec#Types)
- [Go by Example : Valeurs](https://gobyexample.com/fr/values)
