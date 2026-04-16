---
title: Constantes et iota (énumérations)
sidebar:
  order: 4
  label: 2.4 Constantes et iota (énumérations)
---

## Contexte

`iota` est un identifiant prédéclaré en Go qui représente des constantes entières non typées successives. Il est utilisé pour créer facilement des énumérations (enums).

- `iota` est remis à `0` au début de chaque bloc `const`.
- Dans le bloc, chaque ligne `const` incrémente `iota` de 1.

## Exemple

Définir les jours de la semaine et des drapeaux binaires avec `iota`.

## Code exemple

```go
package main

import "fmt"

const (
    Dimanche = iota  // 0
    Lundi            // 1
    Mardi            // 2
    Mercredi         // 3
    Jeudi            // 4
    Vendredi         // 5
    Samedi           // 6
)

const (
    Lecture = 1 << iota  // 1 << 0 = 1
    Ecriture             // 1 << 1 = 2
    Execution            // 1 << 2 = 4
)

func main() {
    fmt.Println(Dimanche, Lundi, Mardi)
    fmt.Println(Lecture, Ecriture, Execution)
}
```

## Sortie

```bash
0 1 2
1 2 4
```

## Liens utiles

- [Spécification Go : Iota](https://go.dev/ref/spec#Iota)
- [Go by Example : Constantes et iota](https://gobyexample.com/fr/constants)
