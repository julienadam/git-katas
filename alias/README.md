# Git kata: Les alias

Avec git on écrit beaucoup de commandes. Ceci peu rapidement devenir fastidieux, surtout pour des commandes avec beaucoup de paramètres. Git permet de créer des alias pour certaines commandes, ce qui raccourcit assez largement le temps passé à les taper et réduit le risque d'erreur de frappe.

Les aliases sont stockés dans la configuration git et peuvent donc être accessibles au niveau système, global ou local. Système est valide pour tous les utilisateurs de la machine, global est la configuration liée à votre utilisateur, local est spécifique au dépôt.

## Mise en place

1. Lancez `source setup.sh` (ou `.\setup.ps1` sous PowerShell)

## Étapes

1. Consultez votre configuration avec `git config --list`
2. Ajoutez un nouvel alias avec \
 `git config --global alias.lol 'log --oneline --graph --all'`\
 Il vous permet d'appeler `git lol` comme alternative à `git log --oneline --graph --all`
3. Lancez l'alias `git lol`
4. Lancez la commande complète `git log --oneline --graph --all`\
Voyez-vous une différence dans la sortie ?
5. Créez un nouvel alias, local cette fois, qui liste les commits dont vous être l'auteur \
`git config --local alias.lome "log --author=\"$(git config --get user.name)\""`
6. Lancez votre alias `git lome`\
 Qu'affiche-t-il ?
7. Affichez votre configuration git et leur source avec `git config --list --show-origin`\
 Pouvez-vous trouvez les définitions de vos aliases ?
8. Essayez de lancer `git lome` dans un dépôt différent. Cela fonctionne-t-il ?
9. Retirez l'alias `git lol`avec `git config --global --unset alias.lol`

## Commandes utiles

- `git config --list`
- `git config --list --show-origin`
- `git config --get <configuration>`
- `git config --unset <configuration>`
