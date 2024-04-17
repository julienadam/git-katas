# Git Kata: Sauvez le soldat commit

Dans ce dépôt se trouve le Saint Graal dans le fichier `holygrail.txt`. Malheureusement, un git reset un peu trop zélé a placé la branche dans l'état initial et le Saint Graal est maintenant perdu ! Il est temps de réparer cette erreur tragique.

## Mise en place

1. Lancez le script `source setup.sh` sous Linux ou `.\setup.ps1` dans PowerShell sous Windows

## Étapes

On vient tout juste de faire un reset de la branche `master` sur le commit initial. Nous allons récupérer le fichier perdu.

1. Utilisez `git log` pour consulter l'historique
2. Vérifiez avec `ls` que `holygrail.txt` n'est pas dans le répertoire de travail
3. Utilisez `git reflog` pour trouver le commit qui a ajouté `holygrail.txt`
4. Utilisez `git reset --hard` pour récupérer cette ancienne version
5. Utilisez `git log` et `ls` pour vérifier l'historique et le contenu, notez l'id du commit contenant `holygrail.txt`
6. Revenez en arrière avec `git reset --hard initial-commit`
7. Utilisez `git cherry-pick` pour réintroduire `holygrail.txt`
8. Comparer l'historique et le répertoire de travail par rapport à la version qui utilisait `git reset`
9. Revenez en arrière à nouveau avec `git reset --hard initial-commit`
10. Forcez le garbage collector avec `git gc`
11. Tentez à nouveau une restauration avec l'une des méthodes précédentes
12. Cette fois ça ne marche plus, les commits sont perdus !

## Commandes utiles

- `git reflog`
- `git cherry-pick`
- `git reset --hard`
- `git log`
