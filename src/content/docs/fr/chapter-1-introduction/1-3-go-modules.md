---
title: Les modules Go
sidebar:
  order: 3
  label: 1.3 Les modules Go
---

## Contexte

Un **module Go** est un ensemble de packages Go versionnés ensemble comme une unité. Les modules remplacent l'ancien flux de travail basé sur `GOPATH` et fournissent :

- **Versionnage** – Les versions sémantiques (v1.2.3) sont obligatoires.
- **Gestion des dépendances** – `go.mod` liste les modules requis et leurs versions.
- **Construire reproductibles** – `go.sum` assure l'intégrité.

Le système de modules a été introduit dans Go 1.11 et est devenu le défaut à partir de Go 1.16.

## Fichiers principaux

- `go.mod` – Définit le chemin du module (ex. `github.com/utilisateur/projet`) et ses dépendances.
- `go.sum` – Contient les sommes de contrôle des dépendances pour vérifier leur intégrité.

## Commandes de base

| Commande               | Objectif                                                          |
| ---------------------- | ----------------------------------------------------------------- |
| `go mod init <module>` | Crée un nouveau module dans le répertoire courant.                |
| `go get <module>`      | Ajoute une dépendance (ou la met à jour).                         |
| `go mod tidy`          | Supprime les dépendances inutilisées et ajoute celles manquantes. |
| `go mod vendor`        | Copie les dépendances dans un dossier `vendor/` (optionnel).      |

## Exemple

Créez un nouveau module nommé "bonjour".

## Code exemple

```bash
mkdir monprojet
cd monprojet
go mod init bonjour
```

## Sortie

```bash
go: creating new go.mod: module bonjour
```

Le fichier `go.mod` contient alors :

```
module bonjour

go 1.24
```

## Ajouter une dépendance

```bash
go get rsc.io/quote
```

Cela met à jour `go.mod` et télécharge le module.

## Liens utiles

- [Utiliser les modules Go (officiel)](https://go.dev/doc/modules/managing-dependencies)
- [Référence des modules Go](https://go.dev/ref/mod)
- [Blog : Utiliser les modules Go](https://go.dev/blog/using-go-modules)
