---
title: Commandes essentielles
sidebar:
  order: 5
  label: 1.5 Commandes essentielles
---

## Contexte

La commande `go` est l'interface principale de la chaîne d'outils Go. Voici les sous‑commandes les plus importantes utilisées quotidiennement.

## Détail des sous‑commandes

### `go run`

Compile et exécute un programme Go en une seule étape. Le binaire compilé est placé dans un répertoire temporaire et supprimé après exécution.

```bash
go run main.go
```

Vous pouvez passer des arguments au programme après un séparateur `--` :

```bash
go run main.go -- arg1 arg2
```

### `go build`

Compile le package courant et ses dépendances. Pour un package `main`, il produit un binaire exécutable. Pour un package non‑principal, il compile et ignore le résultat (utile pour vérifier les erreurs).

```bash
# Construire l'exécutable (nom = nom du dossier)
go build

# Construire avec un nom de sortie personnalisé
go build -o monapp

# Construire pour un système d'exploitation différent
GOOS=windows GOARCH=amd64 go build
```

### `go test`

Exécute les tests définis dans les fichiers `*_test.go`. Il découvre les fonctions nommées `TestXxx(t *testing.T)` et les exécute.

```bash
# Exécuter tous les tests du répertoire courant
go test

# Sortie verbeuse
go test -v

# Exécuter une fonction de test spécifique
go test -run=TestAddition

# Exécuter les tests avec couverture
go test -cover

# Exécuter les benchmarks
go test -bench=.
```

### `go fmt`

Formate les fichiers source Go selon le style officiel (pas de tabulation, indentation cohérente). Cette commande réécrit les fichiers sur place. Elle peut être exécutée sans risque sur n'importe quel code Go.

```bash
# Formater le répertoire courant
go fmt

# Formater tous les packages du module
go fmt ./...
```

### `go vet`

Signale les constructions suspectes qui sont probablement des bogues, comme du code inatteignable, des formats de chaîne incorrects, ou des conditions de concurrence (avec `-race`). Il ne produit généralement pas de faux positifs.

```bash
go vet
go vet ./...
```

### `go mod tidy`

Nettoie les fichiers `go.mod` et `go.sum` en ajoutant les dépendances manquantes et en supprimant celles inutilisées. Exécutez‑le toujours avant de valider les modifications d'un module.

```bash
go mod tidy
```

## Exemple

Compilez et exécutez un programme simple.

## Code exemple

```bash
go run main.go
```

## Sortie

```bash
Bonjour, Go !
```

## Liens utiles

- [Documentation de la commande go](https://go.dev/doc/cmd)
- [Comment écrire du code Go](https://go.dev/doc/code)
