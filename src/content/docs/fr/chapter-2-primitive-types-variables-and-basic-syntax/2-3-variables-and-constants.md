---
title: Variables et constantes
sidebar:
  order: 3
  label: 2.3 Variables et constantes
---

## Contexte

Go propose plusieurs façons de déclarer des variables et des constantes.

### Déclarations de variables

1. **`var` avec type** – `var nom string`
2. **`var` avec initialisation** – `var nom = "Alice"` (type inféré)
3. **Assignation courte `:=`** – `nom := "Alice"` (uniquement à l'intérieur des fonctions)
4. **Variables multiples** – `var x, y int = 1, 2` ou `x, y := 1, 2`

### Constantes

- Déclarées avec le mot‑clé `const`.
- Ne peuvent pas être modifiées après déclaration.
- Peuvent être non typées (ex. `const Pi = 3.14`).

## Exemple

Démontrer différentes déclarations de variables et constantes.

## Code exemple

```go
package main

import "fmt"

const Pi = 3.14159
const (
    StatusOK = 200
    StatusNotFound = 404
)

func main() {
    var nom string = "Alice"
    var age = 30
    ville := "Paris"
    var x, y int = 10, 20
    a, b := "bonjour", true

    fmt.Println(nom, age, ville)
    fmt.Println(x, y, a, b)
    fmt.Println(Pi, StatusOK, StatusNotFound)
}
```

## Sortie

```bash
Alice 30 Paris
10 20 bonjour true
3.14159 200 404
```

## Liens utiles

- [Spécification Go : Variables](https://go.dev/ref/spec#Variables)
- [Go by Example : Variables](https://gobyexample.com/fr/variables)
- [Go by Example : Constantes](https://gobyexample.com/fr/constants)
