---
title: Votre premier programme
sidebar:
  order: 6
  label: 1.6 Votre premier programme
---

## Contexte

Chaque programme Go est composé de **packages**. Un package nommé `main` est spécial : il définit un programme exécutable. Le point d'entrée est une fonction nommée `main` sans paramètres et sans valeur de retour.

## Structure d'un fichier source Go

```go
package main                     // Déclaration du package

import "fmt"                     // Importation (bibliothèque standard)

func main() {                    // Fonction d'entrée
    fmt.Println("Bonjour, monde")  // Instruction
}
```

## Explication

- `package main` – Déclare que ce fichier appartient au package `main`.
- `import "fmt"` – Importe le package `fmt` pour les entrées/sorties formatées.
- `func main()` – Le programme commence ici. Pas d'arguments, pas de retour.
- `fmt.Println` – Affiche une ligne sur la sortie standard.

## Exécution du programme

Enregistrez le code sous `main.go`, puis dans un terminal :

```bash
go run main.go
```

## Exemple

Créez un fichier `main.go` avec le contenu ci‑dessous.

## Code exemple

```go
package main

import "fmt"

func main() {
    fmt.Println("Bonjour, monde")
}
```

## Sortie

```bash
Bonjour, monde
```

## Liens utiles

- [Premiers pas avec Go](https://go.dev/doc/tutorial/getting-started)
- [Une visite de Go](https://go.dev/tour/)
- [Comment écrire du code Go](https://go.dev/doc/code)
