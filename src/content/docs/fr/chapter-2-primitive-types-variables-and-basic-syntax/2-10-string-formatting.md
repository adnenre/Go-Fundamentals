---
title: Formatage de chaînes
sidebar:
  order: 10
  label: 2.10 Formatage de chaînes
---

## Contexte

Le package `fmt` fournit un formatage de chaînes puissant avec des verbes similaires à `printf` en C.

Verbes courants :

- `%v` – format par défaut
- `%+v` – structure avec noms de champs
- `%#v` – représentation syntaxique Go
- `%T` – type
- `%d` – entier (décimal)
- `%f` – flottant
- `%s` – chaîne
- `%q` – chaîne entre guillemets
- `%x` – hexadécimal
- `%p` – pointeur

## Exemple

Formater différents types de données.

## Code exemple

```go
package main

import "fmt"

type Personne struct {
    Nom string
    Age int
}

func main() {
    p := Personne{"Alice", 30}
    fmt.Printf("Défaut : %v\n", p)
    fmt.Printf("+v : %+v\n", p)
    fmt.Printf("#v : %#v\n", p)
    fmt.Printf("Type : %T\n", p)

    n := 42
    f := 3.14159
    s := "bonjour"

    fmt.Printf("Entier : %d, Hex : %x, Bin : %b\n", n, n, n)
    fmt.Printf("Flottant : %.2f\n", f)
    fmt.Printf("Chaîne : %s, Entre guillemets : %q\n", s, s)
}
```

## Sortie

```bash
Défaut : {Alice 30}
+v : {Nom:Alice Age:30}
#v : main.Personne{Nom:"Alice", Age:30}
Type : main.Personne
Entier : 42, Hex : 2a, Bin : 101010
Flottant : 3.14
Chaîne : bonjour, Entre guillemets : "bonjour"
```

## Liens utiles

- [Documentation du package fmt](https://pkg.go.dev/fmt)
- [Go by Example : Formatage de chaînes](https://gobyexample.com/fr/string-formatting)
