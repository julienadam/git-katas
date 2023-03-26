# Git Kata: Les bases du *staging*

Ce kata est consacré à l'examen de la *staging area* (zone de transit)

Dans git on travaille sur 3 zones distinctes :

* Le répertoire de travail où l'on va faire nos changements
* La zone de *staging* où résident les changements qu'on a ajouté via la commande `git add` 
* Le dépôt (*repository*) où sont stockés les *commits*, formant l'historique. Pour y transférer les changements depuis la zone de *staging*, on utilise la commande `git commit`

Un fichier peut avoir des changements à la fois dans le répertoire de travail et dans la zone de *staging*. Ces changements ne sont pas nécessairement les mêmes

On travaillera aussi avec `git restore` pour rétablir les changements mis en *staging*, et `git checkout` pour rétablir un fichier dans un état précédent.

## Mise en place

1. Lancez le script `source setup.sh` sous Linux ou `.\setup.ps1` dans PowerShell sous Windows

## Étapes

Vous travaillez dans votre propre repository. Vous y trouverez un fichier nommé `file.txt`.

1. Quel est le contenu de `file.txt`?
2. Écrasez le contenu de `file.txt`: `echo 2 > file.txt` afin de changer l'état du fichier dans le répertoire de travail (`sc file.txt '2'` sous PowerShell)
3. Que vous dit `git diff` ? Pourquoi ?
4. Que vous dit `git diff --staged` ? Pourquoi est-ce vide ?
5. Lancez `git add file.txt` pour mettre le changement dans la zone de *staging* depuis le répertoire de travail.
6. Que vous dit `git diff` ?
7. Que vous dit  `git diff --staged` ?
8. Écrasez le contenu de `file.txt`: `echo 3 > file.txt` afin de changer l'état du fichier dans le répertoire de travail (`sc file.txt '3'` sous PowerShell).
9. Que vous dit `git diff` ?
10. Que vous dit  `git diff --staged` ?
11. Expliquez ce qui se passe
12. Lancez `git status` et observez que `file.txt` est présent 2 fois dans la sortie.
13. Lancez `git restore --staged file.txt` pour retirer les changements du *staging*
14. Que vous dit `git status` maintenant ?
15. Ajoutez le changement au *staging* et faites un *commit* (`git commit`)
16. A quoi ressemble l'historique ? (`git log`)
17. Écrasez le contenu de `file.txt`: `echo 4 > file.txt` (`sc file.txt '4'` sous PowerShell)
18. Quel est le contenu de `file.txt`?
19. Que vous dit `git status` ?
20. Lancez `git restore file.txt`
21. Quel est le contenu de `file.txt`?
22. Que vous dit `git status` ?

## Commandes utiles

- `git add`
- `git commit`
- `git commit -m "Mon message rapide"`
- `git log`
- `git log -n 5`
- `git log --oneline`
- `git log --oneline --graph`
- `git restore --staged`

## Alias de commandes

Vous pouvez mettre en place des alias de commandes comme ceci :
`git config --global alias.lol 'log --oneline --graph --all'`

Ca pourra vous être utile.
