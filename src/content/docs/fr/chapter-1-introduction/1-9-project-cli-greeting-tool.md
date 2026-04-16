---
title: Projet – Outil de salutation en CLI
sidebar:
  order: 9
  label: 1.9 Projet – Outil de salutation en CLI
---

## Contexte

Ce projet combine plusieurs concepts de base : lire une entrée utilisateur (avec `bufio`), manipuler des chaînes (`strings.TrimSpace`), et afficher une sortie formatée.

Le programme va :

1. Demander le nom de l'utilisateur.
2. Demander sa couleur préférée.
3. Afficher une salutation personnalisée.

## Explication détaillée des packages utilisés

- `bufio` – Fournit des entrées/sorties tamponnées, efficaces pour lire des lignes entières.
- `os.Stdin` – L'entrée standard (le terminal).
- `strings.TrimSpace` – Supprime les espaces et les sauts de ligne au début et à la fin.
- `fmt.Printf` – Affichage formaté avec `%s` pour les chaînes et `\n` pour les sauts de ligne.

## Code pas à pas

```go
package main

import (
    "bufio"
    "fmt"
    "os"
    "strings"
)

func main() {
    // Crée un lecteur tamponné à partir de l'entrée standard
    lecteur := bufio.NewReader(os.Stdin)

    // Demande le nom
    fmt.Print("Entrez votre nom : ")
    nom, err := lecteur.ReadString('\n')
    if err != nil {
        fmt.Println("Erreur de lecture :", err)
        return
    }
    nom = strings.TrimSpace(nom) // enlève le saut de ligne et les espaces

    // Demande la couleur
    fmt.Print("Entrez votre couleur préférée : ")
    couleur, err := lecteur.ReadString('\n')
    if err != nil {
        fmt.Println("Erreur de lecture :", err)
        return
    }
    couleur = strings.TrimSpace(couleur)

    // Affiche la salutation
    fmt.Printf("\nBonjour %s ! Votre couleur préférée %s est superbe !\n", nom, couleur)
}
```

## Exemple d'interaction

```bash
Entrez votre nom : Alice
Entrez votre couleur préférée : bleu

Bonjour Alice ! Votre couleur préférée bleu est superbe !
```

## Gestion des erreurs

Si l'utilisateur presse Ctrl+D (fin de fichier) ou qu'une erreur survient, le programme affiche une erreur et se termine proprement.

## Extensions (optionnel)

- Ajoutez de la couleur à la sortie en utilisant des codes ANSI.
- Validez que la couleur n'est pas vide.
- Utilisez une boucle pour redemander une saisie invalide.

## Liens utiles

- [Documentation du package bufio](https://pkg.go.dev/bufio)
- [Documentation du package strings](https://pkg.go.dev/strings)
- [Documentation du package fmt](https://pkg.go.dev/fmt)
- [Go by Example : Arguments en ligne de commande](https://gobyexample.com/fr/command-line-arguments)
