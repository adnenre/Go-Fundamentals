---
title: Entrées/Sorties basiques
sidebar:
  order: 5
  label: 2.5 Entrées/Sorties basiques
---

## Contexte

Go propose plusieurs façons de lire des entrées et d'écrire des sorties. Les plus courantes sont :

- **Sortie** : `fmt.Print`, `fmt.Println`, `fmt.Printf`
- **Entrée** : `fmt.Scan`, `fmt.Scanln`, `fmt.Scanf`, et `bufio` pour des lignes entières.

## Exemple

Lire un nom et un âge depuis l'utilisateur, puis afficher une salutation.

## Code exemple

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

    fmt.Print("Entrez votre nom : ")
    nom, _ := lecteur.ReadString('\n')
    nom = strings.TrimSpace(nom)

    fmt.Print("Entrez votre âge : ")
    ageStr, _ := lecteur.ReadString('\n')
    age, _ := strconv.Atoi(strings.TrimSpace(ageStr))

    fmt.Printf("Bonjour %s, vous avez %d ans.\n", nom, age)
}
```

## Exemple d'interaction

```bash
Entrez votre nom : Alice
Entrez votre âge : 30
Bonjour Alice, vous avez 30 ans.
```

## Liens utiles

- [Documentation du package fmt](https://pkg.go.dev/fmt)
- [Documentation du package bufio](https://pkg.go.dev/bufio)
