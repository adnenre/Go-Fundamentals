---
title: Installer Go
sidebar:
  order: 2
  label: 1.2 Installer Go
---

## Contexte

Pour commencer à programmer en Go, vous devez installer la chaîne d'outils Go (compilateur, bibliothèque standard, commandes en ligne). Go est supporté sur Linux, macOS, Windows et plusieurs autres plateformes.

## Étapes d'installation par système d'exploitation

### Linux

1. Téléchargez l'archive la plus récente depuis [go.dev/dl](https://go.dev/dl/), par exemple `go1.24.0.linux-amd64.tar.gz`.
2. Supprimez toute installation Go précédente (généralement dans `/usr/local/go`) :
   ```bash
   sudo rm -rf /usr/local/go
   ```
3. Extrayez l'archive dans `/usr/local` :
   ```bash
   sudo tar -C /usr/local -xzf go1.24.0.linux-amd64.tar.gz
   ```
4. Ajoutez `/usr/local/go/bin` à votre variable d'environnement `PATH` (ajoutez à `~/.profile` ou `~/.bashrc`) :
   ```bash
   export PATH=$PATH:/usr/local/go/bin
   ```

### macOS

- Avec l'installeur officiel : téléchargez le fichier `.pkg` depuis [go.dev/dl](https://go.dev/dl/) et exécutez‑le.
- Avec Homebrew : `brew install go`.

### Windows

- Téléchargez le programme d'installation MSI depuis [go.dev/dl](https://go.dev/dl/) et exécutez‑le. Il configurera automatiquement la variable d'environnement `PATH`.

## Vérifier l'installation

Après l'installation, ouvrez un nouveau terminal et exécutez :

## Code exemple

```bash
go version
```

## Sortie

```bash
go version go1.24.0 linux/amd64
```

## Vérification supplémentaire

Affichez l'environnement Go :

```bash
go env
```

Cela montre des variables comme `GOROOT` (chemin d'installation), `GOPATH` (ancien espace de travail, inutile avec les modules), et `GOOS`/`GOARCH`.

## Liens utiles

- [Télécharger Go](https://go.dev/dl/)
- [Instructions officielles d'installation](https://go.dev/doc/install)
- [Configuration de Go sous Windows](https://go.dev/doc/install/windows)
