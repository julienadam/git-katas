# Git Kata: Les bases des branches

## Mise en place

1. Lancez `source setup.sh` (ou `.\setup.ps1` sous PowerShell)

## Étapes

A nouveau, vous êtes dans une branche dédiée, cette fois nous allons jongler entre plusieurs branches pour démontrer à quel point les branches sont légères avec Git.

Astuce : `git switch` permet de se déplacer d'une branche à l'autre

1. Utilisez `git branch`pour afficher les 2 branches de cet exercice
2. Sur quelle branche se trouve-t-on ?
3. Utilisez `git branch mybranch` pour créer une nouvelle branche nommée _mybranch_
4. Utilisez `git branch` pour afficher la nouvelle branche
5. Utilisez `git switch mybranch` pour vous placer dans la nouvelle branche.
6. Quels changements voyez-vous dans la sortie de git status quand vous vous déplacez entre _master_ et _mybranch_ ?
7. Qu'est ce qui change au niveau du répertoire de travail ?
8. Assurez vous d'être dans la branche _mybranch_ avant de continuer
9. Créez un fichier `file1.txt` contenant votre nom
10. Ajoutez le fichier et faites un `commit` avec ce changement.
11. Utilisez `git log --oneline --graph` pour voir votre branche pointant sur ce dernier commit.
12. Retournez sur la branche _master_
13. Utilisez `git log --oneline --graph` et prenez note du fait que le commit que vous avez fait dans _mybranch_ est absent de la branche _master_ !
14. Créez un nouveau `file2.txt` et faites un commit de ce fichier.
15. Utilisez `git log --oneline --graph --all` pour voir votre branche _master_ pointer vers ce nouveau commit et voyez que les 2 branches ont 2 commits de tête différents.
16. Retournez sur _mybranch_.
17. Que s'est-il passé sur votre répertoire de travail ? pouvez-vous voir le fichier `file2.txt` ?
18. utilisez `git diff mybranch master` pour voir la différence entre vos branches.

## Commandes utiles

- `git switch`
- `git switch -c`
- `git log --oneline --graph`
- `git branch`
- `git diff`
