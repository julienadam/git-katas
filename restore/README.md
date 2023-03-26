# Git kata: Restaurer des fichiers

On fait tous des erreurs. Parfois on fait des changements qu'on aurait préféré ne pas faire, ou alors on place en staging des changements par erreur.

C'est à ce moment qu'intervient `git restore`.

## Mise en place

1. Lancez `source setup.sh` (ou `.\setup.ps1` sous PowerShell)

## Étapes

1. Appelez `git status` Quels changements ont été faits sur ce dépôt ?
2. Restaurez le fichier `foo.txt` en utilisant `git restore foo.txt`
3. Appelez `git status` à nouveau. Que s'est-il passé sur `foo.txt`?
4. Retirez du staging les modifications de `bar.txt` en utilisant `git restore --staged bar.txt`
5. Appelez `git status` une fois encore. Que s'est-il passé sur `foo.txt`?
6. Restaurez le fichier `bar.txt` en utilisant `git restore bar.txt`
7. Appelez `git status` une fois encore.  Que s'est-il passé sur `foo.txt`?
8. Appelez `git log --oneline`. Avez-vous vu le tag ?
9. Restaurez le contenu de `foo.txt` à leur version précédente en utilisant `git restore -s v1.0.0 foo.txt`
10. Appelez `git status` une fois encore. Que s'est-il passé sur `foo.txt`?

## Commandes utiles

- `git status`
- `git log --oneline`
- `git restore`
- `git restore --staged`