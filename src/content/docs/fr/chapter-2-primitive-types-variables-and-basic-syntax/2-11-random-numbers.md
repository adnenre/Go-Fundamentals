---
title: Nombres aléatoires
sidebar:
  order: 11
  label: 2.11 Nombres aléatoires
---

## Contexte

Go fournit la génération de nombres aléatoires dans le package `math/rand`. Pour un aléatoire cryptographique, utilisez `crypto/rand`.

Fonctions importantes :

- `rand.Intn(n)` – entier aléatoire dans `[0, n)`
- `rand.Int()` – entier aléatoire non négatif
- `rand.Float64()` – flottant aléatoire dans `[0.0, 1.0)`
- `rand.Seed(seed)` – initialise le générateur (obsolète depuis Go 1.20+ ; maintenant automatique)

Depuis Go 1.20, le générateur aléatoire global est initialisé automatiquement au démarrage du programme.

## Exemple

Générer des nombres aléatoires.

## Code exemple

```go
package main

import (
    "fmt"
    "math/rand"
    "time"
)

func main() {
    // Entier aléatoire entre 0 et 99
    fmt.Println("Entier aléatoire 0-99 :", rand.Intn(100))

    // Flottant aléatoire entre 0.0 et 1.0
    fmt.Println("Flottant aléatoire :", rand.Float64())

    // Entier aléatoire non négatif
    fmt.Println("Entier aléatoire :", rand.Int())

    // Pour des séquences différentes à chaque exécution (encore possible mais optionnel)
    rand.NewSource(time.Now().UnixNano())
    fmt.Println("Aléatoire initialisé :", rand.Intn(100))
}
```

## Sortie (exemple, varie à chaque exécution)

```bash
Entier aléatoire 0-99 : 42
Flottant aléatoire : 0.123456789
Entier aléatoire : 1234567890123456789
Aléatoire initialisé : 87
```

## Liens utiles

- [Documentation du package math/rand](https://pkg.go.dev/math/rand)
- [Go by Example : Nombres aléatoires](https://gobyexample.com/fr/random-numbers)
