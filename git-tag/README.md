# Git Kata: Ajouter des *tags* aux *commits*

## Mise en place

1. Lancez `source setup.sh` (ou `.\setup.ps1` sous PowerShell)

## Motivation

Les [Tags](https://git-scm.com/book/en/v2/Git-Basics-Tagging) sont un moyen pratique pour suivre les *commits* qui correspondents à un changement de version de logiciel par exemple. Un moyen de les utiliser consiste à les combiner avec les branches, en ajoutant un tag sur les commits qui font augmenter le numéro de version. Par exemple dans une branche `version/1.1` ou pourrait suivre l'évolution de la version 1.1 et mettre des tags sur les commits correspondant à la version 1.1.1, 1.1.2 etc. Bien entendu, les tags peuvent être utilisés sans branches également.

Il y a 2 types de tags, les tags avec et sans annotations. Les tags annotés contiennent des informations supplémentaires, par exemple une descriptions, en plus du nom. Les tags non-annotés, ou tags légers, ne possèdent qu'un nom. Dans certains cas un tag léger suffit car les informations du nom du tag et les messages de commit sont assez descriptives. 

## Étapes

Pour rester simple, nous ne travaillerons que sur la branche master dans ce kata. Quelques tags ont déjà été créés.

1. Trouvez les tags déjà créés
1. Faites un nouveau commit et appliquer dessus un tag annoté
1. Il y a quelques commits dans le repo, ajoutez un tag à un commit quelconque dans l'historique
1. Il y a un tag annoté dans le dépôt, quel est le message ?
1. Certains tags ne sont pas utiles, effacez les

## Commandes utiles

- `git tag`
- `git tag -d <tag>`
- `git tag --list <pattern>`
- `git push --tags <branch>`
- `git rev-parse <tag>`
- `git show`
