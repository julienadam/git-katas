# Git katas: Interactive rebase with --autosquash option

Vous avez travaillé sur une nouvelle fonctionnalité nommée Hello World.

La fonctionnalité est terminée (avec documentation et tests !) mais il y a une erreur de frappe dans la documentation.

Il faut réparer ça et faire un rebase pour obtenir un historique parfait.

Par chance, il existe un tag `v0.0` posé juste avant de travailler sur la fonctionnalité.

Avec quelques options avancées de `git commit` et `git rebase` nous allons pouvoir réaliser cette modification sans difficulté.

## Mise en place

1. Lancez le script `source setup.sh` sous Linux ou `.\setup.ps1` dans PowerShell sous Windows

## Étapes

1. Explorez le dépôt et l'historique pour trouver dans quel commit le fichier de documentation a été ajouté.
2. Corrigez le `README.md` et mettez le en staging.
3. Créez le commit avec la commande `git commit --fixup=<id du commit à corriger>`.
4. Lancez `git rebase --autosquash --interactive v0.0` pour afficher la recette de rebase générée automatiquement.
5. Utilisez `git log` pour constater la beauté de l'historique corrigé.

### Commandes utiles

- `ls -l`                           # lister les fichiers
- `tail -n +1 *`                    # afficher le contenu des fichiers
- `git log --oneline`               # afficher l'historique
- `git log --stat`                  # historique avec résumé des changements
- `git log --patch`                 # historique avec diff
- `git show <commit id>`            # modifications d'un commit
- `git add`                         # mettre un fichier en staging
- `git commit --fixup=<commit id>`  # créer un commit avec un message auto-généré
- `git rebase -i <ref>`             # procéder à un rebase vers <ref> et réordonner les commits automatiquement
