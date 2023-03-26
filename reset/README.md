# Git katas: Git reset

Nous pouvons manipuler l'historique à notre guise. Mais attention à ne jouer qu'avec l'historique local. Il est attendu que Les commits publiés soient immuables.

On peut utiliser reset pour retirer des modifications du staging mais cette commande est utile à bien d'autres choses.

## Mise en place

1. Lancez `source setup.sh` (ou `.\setup.ps1` sous PowerShell)

## Étapes

1. A quoi ressemble votre répertoire de travail ?
1. A quoi ressemble le log ? Et le staging ?
1. Essayez de lancer `git reset --soft HEAD~1`
1. Que se passe-t-il sur votre répertoire de travail, sur l'historique et sur le staging ?
1. Lancez `git reset --mixed HEAD~1`
1. Que se passe-t-il sur votre répertoire de travail, sur l'historique et sur le staging ?
1. Lancez `git reset --hard HEAD~1`
1. Que se passe-t-il sur votre répertoire de travail, sur l'historique et sur le staging ?
1. Maintenant essayez `git revert HEAD~1`
1. Que se passe-t-il sur votre répertoire de travail, sur l'historique et sur le staging ?

## Commandes utiles

- `git log --oneline`
- `git commit --amend`
- `git status`
- `git reset --soft`
- `git reset --mixed`
- `git reset --hard`
- `git revert`

## Plus d'informations

Extrait de la section "Recap" de [https://git-scm.com/book/en/v2/Git-Tools-Reset-Demystified].

La commande reset écrase ces trois arbres dans un ordre spécifique, et s'arrête quand on lui dit :

1. Déplace ce vers quoi la branche HEAD pointe (s'arrête ici si --soft)
2. Met le staging dans le même état que HEAD (s'arrête ici si --hard)
3. Met le répertoire de travail dans le même état que le staging
