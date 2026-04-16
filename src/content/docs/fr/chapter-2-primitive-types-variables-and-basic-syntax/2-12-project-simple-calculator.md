---
title: Projet – Calculatrice simple
sidebar:
  order: 12
  label: 2.12 Projet – Calculatrice simple
---

## Contexte

Construisez une calculatrice en ligne de commande qui lit deux nombres et un opérateur (`+`, `-`, `*`, `/`), puis affiche le résultat.

Ce projet combine :

- Lecture des entrées utilisateur (`bufio`, `fmt.Scanln`)
- Conversion de types (`strconv.ParseFloat`)
- Logique conditionnelle (`switch`)
- Gestion d'erreurs

## Code pas à pas

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
    lecteur := bufio.NewReader(os.Stdin)

    // Lire le premier nombre
    fmt.Print("Entrez le premier nombre : ")
    num1Str, _ := lecteur.ReadString('\n')
    num1, err1 := strconv.ParseFloat(strings.TrimSpace(num1Str), 64)
    if err1 != nil {
        fmt.Println("Nombre invalide")
        return
    }

    // Lire l'opérateur
    fmt.Print("Entrez l'opérateur (+, -, *, /) : ")
    op, _ := lecteur.ReadString('\n')
    op = strings.TrimSpace(op)

    // Lire le deuxième nombre
    fmt.Print("Entrez le deuxième nombre : ")
    num2Str, _ := lecteur.ReadString('\n')
    num2, err2 := strconv.ParseFloat(strings.TrimSpace(num2Str), 64)
    if err2 != nil {
        fmt.Println("Nombre invalide")
        return
    }

    // Effectuer le calcul
    var resultat float64
    switch op {
    case "+":
        resultat = num1 + num2
    case "-":
        resultat = num1 - num2
    case "*":
        resultat = num1 * num2
    case "/":
        if num2 == 0 {
            fmt.Println("Erreur : division par zéro")
            return
        }
        resultat = num1 / num2
    default:
        fmt.Println("Opérateur invalide")
        return
    }

    fmt.Printf("%g %s %g = %g\n", num1, op, num2, resultat)
}
```

## Exemple d'interaction

```bash
Entrez le premier nombre : 10
Entrez l'opérateur (+, -, *, /) : /
Entrez le deuxième nombre : 3
10 / 3 = 3.3333333333333335
```

## Autre exemple (division par zéro)

```bash
Entrez le premier nombre : 5
Entrez l'opérateur (+, -, *, /) : /
Entrez le deuxième nombre : 0
Erreur : division par zéro
```

## Liens utiles

- [Documentation du package strconv](https://pkg.go.dev/strconv)
- [Documentation du package bufio](https://pkg.go.dev/bufio)
- [Documentation du package fmt](https://pkg.go.dev/fmt)
