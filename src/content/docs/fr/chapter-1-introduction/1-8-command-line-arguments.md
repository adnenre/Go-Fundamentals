---
title: Arguments en ligne de commande
sidebar:
  order: 8
  label: 1.8 Arguments en ligne de commande
---

## Contexte

Lorsque vous exécutez un programme depuis le terminal, vous pouvez lui passer des arguments. En Go, ils sont disponibles via `os.Args` – une slice de chaînes où `os.Args[0]` est le nom du programme, et `os.Args[1:]` les arguments.

Pour analyser des indicateurs plus complexes (ex. `-port 8080`), le package `flag` fournit une solution standard.

## Utilisation de `os.Args`

```go
package main

import (
    "fmt"
    "os"
)

func main() {
    // Afficher tous les arguments, y compris le nom du programme
    for i, arg := range os.Args {
        fmt.Printf("args[%d] = %s\n", i, arg)
    }

    // Obtenir les arguments positionnels (sauter le nom du programme)
    if len(os.Args) < 2 {
        fmt.Println("Veuillez fournir au moins un argument")
        return
    }
    premierArg := os.Args[1]
    fmt.Println("Premier argument :", premierArg)
}
```

## Utilisation du package `flag`

Le package `flag` analyse les indicateurs de style Unix (ex. `-nom=valeur`, `--nom valeur`).

```go
package main

import (
    "flag"
    "fmt"
)

func main() {
    var nom string
    var age int
    flag.StringVar(&nom, "nom", "Monde", "nom à saluer")
    flag.IntVar(&age, "age", 0, "âge de la personne")
    flag.Parse()

    fmt.Printf("Bonjour, %s (âge %d)\n", nom, age)
    fmt.Println("Arguments restants :", flag.Args())
}
```

Exécutez avec :

```bash
go run main.go -nom Alice -age 30 extra1 extra2
```

## Sortie

```bash
Bonjour, Alice (âge 30)
Arguments restants : [extra1 extra2]
```

## Exemple

Affichez tous les arguments reçus.

## Code exemple

```go
package main

import (
    "fmt"
    "os"
)

func main() {
    fmt.Println("Arguments :", os.Args)
}
```

## Sortie (si exécuté avec `go run main.go bonjour monde`)

```bash
Arguments : [/tmp/go-build123/b001/exe/main bonjour monde]
```

## Liens utiles

- [Documentation de os.Args](https://pkg.go.dev/os#Args)
- [Documentation du package flag](https://pkg.go.dev/flag)
- [Arguments en ligne de commande en Go (tutoriel)](https://www.digitalocean.com/community/tutorials/command-line-arguments-in-go)
