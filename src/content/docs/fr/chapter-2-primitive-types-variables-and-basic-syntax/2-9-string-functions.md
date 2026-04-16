---
title: Fonctions sur les chaînes
sidebar:
  order: 9
  label: 2.9 Fonctions sur les chaînes
---

## Contexte

Le package `strings` fournit de nombreuses fonctions utilitaires pour la manipulation des chaînes.

Fonctions courantes : `Contains`, `Count`, `HasPrefix`, `HasSuffix`, `Index`, `Join`, `Repeat`, `Replace`, `Split`, `ToLower`, `ToUpper`, `TrimSpace`.

## Exemple

Utiliser plusieurs fonctions sur les chaînes.

## Code exemple

```go
package main

import (
    "fmt"
    "strings"
)

func main() {
    s := "  Bonjour, Go !  "
    fmt.Println("Sans espaces :", strings.TrimSpace(s))
    fmt.Println("Majuscules :", strings.ToUpper(s))
    fmt.Println("Contient 'Go' :", strings.Contains(s, "Go"))
    fmt.Println("Découpage par espace :", strings.Split(s, " "))
    fmt.Println("Remplacer Go par Gophers :", strings.ReplaceAll(s, "Go", "Gophers"))
    fmt.Println("Assemblage :", strings.Join([]string{"a", "b", "c"}, "-"))
}
```

## Sortie

```bash
Sans espaces : Bonjour, Go !
Majuscules :   BONJOUR, GO !
Contient 'Go' : true
Découpage par espace : [  Bonjour,  Go !  ]
Remplacer Go par Gophers :   Bonjour, Gophers !
Assemblage : a-b-c
```

## Liens utiles

- [Documentation du package strings](https://pkg.go.dev/strings)
- [Go by Example : Fonctions sur les chaînes](https://gobyexample.com/fr/string-functions)
