---
title: Qu'est-ce que Go
sidebar:
  order: 1
  label: 1.1 Qu'est-ce que Go
---

## Contexte

Go (aussi appelé Golang) est un langage de programmation open source créé chez Google en 2007 par Robert Griesemer, Rob Pike et Ken Thompson. Il a été annoncé publiquement en novembre 2009, et la première version stable, Go 1.0, est sortie en mars 2012.

Go a été conçu pour répondre aux critiques courantes des autres langages (compilation lente, concurrence lourde, gestion complexe des dépendances) tout en conservant leurs points forts. Ses objectifs principaux sont :

- **Simplicité** – Syntaxe minimale, pas de classes ni d'héritage, pas d'exceptions, pas de génériques jusqu'en 2022 (et ils restent simples).
- **Efficacité** – Compilation en code natif, exécution rapide, faible empreinte mémoire, compilation rapide.
- **Concurrence intégrée** – Les goroutines et les canaux rendent la programmation concurrente sûre et simple.

Go est un langage **statiquement typé**, **compilé** et doté d'un **ramasse‑miettes** (garbage collector). Il est devenu le langage du cloud, alimentant des outils comme Docker, Kubernetes, Terraform, et bien d'autres.

## Historique des versions et fonctionnalités clés

Go suit un cycle de publication semestriel (tous les six mois, en février et août). Chaque version est supportée jusqu'à ce que deux versions plus récentes soient sorties.

- **Go 1.0 (2012-03-28)** – Première version stable, garantie de compatibilité.
- **Go 1.1 (2013-05-13)** – Améliorations de performances, détecteur de concurrence (race detector).
- **Go 1.2 (2013-12-01)** – Limite configurable du nombre de threads, meilleur ordonnanceur.
- **Go 1.3 (2014-06-18)** – Gestion améliorée des piles (stack) des goroutines.
- **Go 1.4 (2014-12-10)** – Support Android, commande `go generate`.
- **Go 1.5 (2015-08-19)** – Compilateur et runtime réécrits en Go, nouveau GC.
- **Go 1.6 (2016-02-17)** – Support HTTP/2, améliorations du GC.
- **Go 1.7 (2016-08-15)** – Introduction du package `context`.
- **Go 1.8 (2017-02-16)** – Pauses GC inférieures à la milliseconde, arrêt gracieux.
- **Go 1.9 (2017-08-24)** – Alias de types.
- **Go 1.10 (2018-02-16)** – Mise en cache des tests, mise en cache automatique des packages.
- **Go 1.11 (2018-08-24)** – **Go Modules** (gestion des dépendances), WebAssembly.
- **Go 1.12 (2019-02-25)** – Améliorations de Go Modules, TLS 1.3.
- **Go 1.13 (2019-09-03)** – Encapsulation des erreurs (error wrapping), amélioration des littéraux numériques.
- **Go 1.14 (2020-02-25)** – Go Modules prêt pour la production, performance de `defer`.
- **Go 1.15 (2020-08-11)** – Améliorations de l'éditeur de liens (20% plus rapide).
- **Go 1.16 (2021-02-16)** – Package `embed`, Go Modules par défaut.
- **Go 1.17 (2021-08-16)** – Convention d'appel basée sur les registres (~5% plus rapide).
- **Go 1.18 (2022-03-15)** – **Génériques** (paramètres de type).
- **Go 1.19 (2022-08-02)** – Raffinements des génériques, commentaires de documentation.
- **Go 1.20 (2023-02-01)** – Optimisation guidée par profil (PGO), conversion slice vers tableau.
- **Go 1.21 (2023-08-08)** – Fonctions intégrées `min`, `max`, `clear`, PGO généralisé.
- **Go 1.22 (2024-02-06)** – Correction de la capture de variable de boucle (portée par itération), améliorations du routage HTTP, prévisualisation des itérateurs `range-over-func`.
- **Go 1.23 (2024-08)** – Nouveaux raffinements et améliorations de performance.
- **Go 1.24 (2025-02)** – Dernière version stable au moment de l'écriture. Voir les notes de version officielles.

## Exemple

Un programme Go minimal consiste en une déclaration `package main` et une fonction `func main()`.

## Code exemple

```go
package main

import "fmt"

func main() {
    fmt.Println("Bonjour, Go !")
}
```

## Sortie

```bash
Bonjour, Go !
```

## Liens utiles

- [Site officiel de Go](https://go.dev/)
- [Historique des versions officielles](https://go.dev/doc/devel/release)
- [Blog : 11 ans de Go](https://go.dev/blog/11year)
- [FAQ Go](https://go.dev/doc/faq)
