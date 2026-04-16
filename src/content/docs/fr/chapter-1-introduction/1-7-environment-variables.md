---
title: Variables d'environnement
sidebar:
  order: 7
  label: 1.7 Variables d'environnement
---

## Contexte

Les variables d'environnement sont des paires clé‑valeur qui affectent le comportement des processus en cours d'exécution. En Go, vous pouvez les lire avec `os.Getenv`, les définir avec `os.Setenv`, et les supprimer avec `os.Unsetenv`.

## Fonctions importantes

| Fonction                | Description                                                           |
| ----------------------- | --------------------------------------------------------------------- |
| `os.Getenv(key)`        | Retourne la valeur sous forme de chaîne (chaîne vide si non définie). |
| `os.LookupEnv(key)`     | Retourne `(valeur, true)` si définie, sinon `("", false)`.            |
| `os.Setenv(key, value)` | Définit une variable d'environnement.                                 |
| `os.Unsetenv(key)`      | Supprime une variable d'environnement.                                |
| `os.Environ()`          | Retourne une slice de chaînes `"clé=valeur"`.                         |

## Exemple

Lisez le répertoire `HOME` (ou `USERPROFILE` sous Windows).

## Code exemple

```go
package main

import (
    "fmt"
    "os"
)

func main() {
    home := os.Getenv("HOME")
    if home == "" {
        home = os.Getenv("USERPROFILE") // Windows
    }
    fmt.Println("Répertoire personnel :", home)

    // Manière plus sûre
    if valeur, ok := os.LookupEnv("PATH"); ok {
        fmt.Println("PATH est défini à :", valeur[:50]) // affiche les 50 premiers caractères
    }
}
```

## Sortie (exemple)

```bash
Répertoire personnel : /home/alice
PATH est défini à : /usr/local/bin:/usr/bin:/bin
```

## Cas d'usage

Les variables d'environnement sont idéales pour la configuration (ex. URL de base de données, clés API) car elles peuvent être modifiées sans recompiler le programme.

## Liens utiles

- [Documentation du package os](https://pkg.go.dev/os#Getenv)
- [Variables d'environnement en Go (tutoriel)](https://go.dev/doc/tutorial/envvars)
