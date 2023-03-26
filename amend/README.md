# Git kata: Amender un commit

Au cours de notre travail nous allons faire beaucoup de commits.

Parfois, on se rend compte qu'on a oublié un détail dans un commit que l'on vient de faire et on veut pouvoir le corriger.

`git commit --amend` est la commande pour gérer ce type de situation : corriger le dernier commit que l'on a fait.

Vous pouvez utiliser `git log -p` ou `git show` pour inspecter le contenu des commits et les changements sur les fichiers modifiés dans les commits.

## Mise en place

1. Lancez `source setup.sh` (ou `.\setup.ps1` sous PowerShell)

## Étapes

1. Que nous dit `git status` ?
2. Que nous dit `git log -p` ?
3. Ajoutez bar.txt au staging
4. Lancez `git commit --amend`
5. Que s'est-t-il passé ? Que nous dit `git log -p` ?
6. Que se passe-t-il si on essaye de lancer `git commit --amend` à nouveau ?

## Commandes utiles

- `git add`
- `git log --oneline --graph`
- `git log -p`
- `git show`
- `git commit --amend`
