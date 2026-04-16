---
title: Structure d'un projet
sidebar:
  order: 4
  label: 1.4 Structure d'un projet
---

## Contexte

Contrairement à beaucoup de langages, Go n'impose **pas** de structure de projet rigide. Cependant, la communauté a adopté des conventions qui fonctionnent bien pour les petits comme pour les grands projets. La règle la plus importante : restez simple.

## Structure minimale (pour un seul exécutable)

```
monprojet/
├── go.mod
├── go.sum
└── main.go
```

## Structure recommandée pour les projets plus gros

```
monprojet/
├── cmd/
│   ├── monapp/          # package main de l'application
│   │   └── main.go
│   └── autreoutil/      # un autre exécutable
│       └── main.go
├── internal/            # packages privés (non importables par d'autres modules)
│   └── monhelper/
│       └── helper.go
├── pkg/                 # packages publics que d'autres modules peuvent importer
│   └── mabibliotheque/
│       └── lib.go
├── api/                 # définitions d'API (OpenAPI, proto gRPC, etc.)
├── web/                 # ressources web (templates, fichiers statiques)
├── scripts/             # scripts de construction, etc.
├── test/                # fichiers de test externes
├── go.mod
└── go.sum
```

## Explication des dossiers clés

- `cmd/` – Contient les commandes exécutables. Chaque sous‑dossier est un package `main` distinct.
- `internal/` – Code **privé** à ce module. Aucun autre module ne peut l'importer.
- `pkg/` – Code **public** destiné à être utilisé par d'autres modules.
- `api/` – Fichiers de contrat d'API (ex. Protocol Buffers, spécifications OpenAPI).
- `web/` – Fichiers statiques, templates, etc.

## Exemple

Structure minimale pour un outil en ligne de commande.

## Code exemple

```bash
moncli/
├── go.mod
├── main.go
```

## Liens utiles

- [Organiser un module Go (officiel)](https://go.dev/doc/modules/layout)
- [Structure de projet Go standard (communauté)](https://github.com/golang-standards/project-layout)
