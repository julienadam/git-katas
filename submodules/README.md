# Git Katas: Submodules

Les sous-modules sont un moyen d'inclure dépôt git dans votre dépôt, en conservant un pointeur vers son `origin`. Ce qui vous permettra de récupérer les sources et de les pousser.

## Mise en place

1. Lancez le script `source setup.sh` sous Linux ou `.\setup.ps1` dans PowerShell sous Windows

## Étapes

Au départ, vous aurez 3 dépôts dans le répertoire `exercise`

- `remote`. Joue le rôle du dépôt distant, celui-ce serait d'ordinaire hébergé sur un serveur git.
- `component` cloned de `remote`.
- `product`, contient le code principal de l'application

1. Placez-vous dans le dépôt `product`
1. Ajoutez un sous-module avec la commande : `git submodule add ../remote include`.
1. Inspectez votre répertoire de travail
1. Que donne `git status` ?
1. Et dans `include`?
1. Lancez `git diff --staged` dans `product`. Ou se trouve l'id du commit indiqué dans la ligne de diff `+Subproject commit ...` ?
1. Faites un commit des modifications dans le dépôt `product`.
1. Placez vous dans le dépôt `component`
1. Ce dépôt est-il au courant qu'il est un sous-module pour un autre dépôt ?
1. Faites une modification, un commit puis un push.
1. Placez-vous dans le dépôt `product`.
1. A l'aide de `git status` ou `git submodule foreach 'git status'` voyez-vous le nouveau commit ?
1. Placez-vous dans le répertoire `include` et faites un `pull`.
1. Vérifiez que le contenu de `include` a bien été mis à jour.
1. Placez-vous dans le dépôt `product` directory. Quel est le statut maintenant ? Examinez aussi `git diff` ?
1. Placez-vous dans le répertoire `include`. Faites une modification, un commit puis un push.
1. Placez-vous dans le répertoire `exercise`. Nous allons cloner le produit pour illustrer l'initialisation d'un clone avec sous-modules.
1. Lancez la commande `git clone product product_alpha`.
1. Allez dans le répertoire `product_alpha`, à quoi ressemble le répertoire de travail ? l'historique ? qu'y a-t-il dans le répertorie `include` ?
1. Lancez `git submodule init`, que contient `include` ?
1. Lancez `git submodule update`, que contient `include` maintenant ?
    (* Note: on peut combiner les deux commandes avec `git submodule update --init`)
1. Le dernier changement fait dans `component` est-il dans `include`?
1. Placez vous dans le dépôt `product`.
1. Faites un commit des modifications `product`. Ne faites pas de push pour le moment !
1. Placez vous dans le dépôt `product_alpha`.
1. Lancez `git submodule update`.
1. Le dernier changement est-il disponible dans `include`?
1. Examinez `git submodule status`. Comparez l'id du commit avec celui du dépôt `component`.
1. Lancez `git submodule update --remote`.
1. Le dernier changement est-il disponible dans `include`?
1. Examinez `git submodule status`. Comparez l'id du commit avec celui du dépôt `component`.

## Commandes utiles

```shell
git diff [--cached] --submodule
git log -p --submodule
```
