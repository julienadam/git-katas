# Git Kata: Grouper les commits avec le squashing

Dans ce kata on souhaite nettoyer un peu l'historique.

Les 5 derniers commits bricolent tous un peu le fichier `file.txt` qui contient la fonctionnalité.

J'aimerais grouper ces 5 commits en un seul.

Pendant que vous y êtes, j'aimerais vraiment que les caractères moches `\n`dans `file.txt` soient retirés de l'historique

## Mise en place

1. Lancez le script `source setup.sh` sous Linux ou `.\setup.ps1` dans PowerShell sous Windows

## Étapes

1. Faites un _squash_ des 5 commits en un et écrivez un bon message de commit (Voir plus bas la section *Plus d'informations*).
1. A quoi ressemble `git log` ?
1. Nettoyez les caractères `\n` dans `file.txt` **SANS AJOUTER** de commit à l'historique.

## Commandes utiles

- `git rebase -i <ref>`
- `git add`
- `git commit --amend`

## Plus d'informations

### 7 règles pour écrit un bon message de commit Git

Tiré de [How to Write a Git Commit Message](https://chris.beams.io/posts/git-commit/)

1. Séparez le titre du corps du message avec une ligne vide
1. Limitez la ligne de titre à 50 caractères
1. Commencez le titre par une majuscule
1. Ne terminez pas le titre avec un point
1. Utilisez l'impératif dans le titre
1. Retournez à la ligne après 72 caractères
1. Utilisez le corps pour expliquer quoi et pourquoi et non pas comment

Exemple
```
Résume les modifications en 50 caractères ou moins

Texte explicatif plus détaillé, si nécessaire. Avec retour à la ligne 
après 72 caractères. Dans certains contextes, la première ligne est
traitée comme le sujet du commit et le reste du texte comme le corps.
La ligne vide séparant le sujet du corps est très important (sauf si 
vous ne mettez aucun corps). De nombreux outils comme `log`, `shortlog`
et `rebase` se mélangent les pinceaux si vous l'oubliez.

Expliquez le problème que le commit résout. Focalisez vous sur pourquoi
vous faites cette modification plutôt que sur comment (le code contient
déjà l'information). Y a-t-il des effets de bords ou des conséquences
contre-intuitives à cette modification ? C'est le bon moment pour les
expliquer.

Les paragraphes suivants sont séparés par des lignes vides.

 - Les listes sont valables également

 - Un tiret ou un astérisque sert de délimiteur pour les éléments de
   la liste, précédé par un espace, mais les conventions varient

Si vous utilisez un système de ticket, mettez les références en base,
comme ceci :

Resolves: #123
See also: #456, #789
```
