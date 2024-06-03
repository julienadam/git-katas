# Git Kata: Configuration de Git

Ce kata n'a pas de script `setup.sh`. Suivez simplement les instructions.

## Téléchargement et installation sous Windows

* Téléchargez Git à cette adresse : [https://git-scm.com/download/win](https://git-scm.com/download/win) (ou utilisez [Chocolatey](https://chocolatey.org/))
* Installez Git en utilisant les paramètres par défaut
* Après installation, ouvrez Git Bash pour les étapes de configuration suivantes

## Configuration initiale de Git

Git a besoin de savoir qui est la personne qui fait des modifications.

Pour cela, vous devez configurer un nom et une adresse email avec les commandes : 

1. `git config --global user.name "John Doe"`
2. `git config --global user.email "johndoe@example.com`

### Choix de l'éditeur

Parfois, Git a besoin d'éditer un fichier qu'il crée pour vous, par exemple, le message dans les commits que vous allez créer.

Par défaut, Git est configuré avec l'éditeur Vim, qui a une courbe d'apprentissage assez raide. Si vous n'êtes pas familier avec Vim, vous pouvez choisir une autre éditeur de votre choix.

Par exemple nano :
- `git config --global core.editor nano`

Ou notepad, sous Windows :
- `git config --global core.editor notepad`

Ou d'autres outils avec lesquels vous êtes à l'aise :

- `git config --global core.editor "'C:/Program Files/Notepad++/notepad++.exe' -multiInst -notabbar -nosession -noPlugin"`
- `git config --global core.editor "atom --wait"`
- `git config --global core.editor "code --wait"`

### Configuration de l'outil de fusion

Lorsque Git devra résoudre des conflits ou afficher les différences entre fichiers, il pourra utiliser un outil de notre choix. Cet outil sera précieux pour visualiser et agir sur les différences graphiquement.

#### Choix 1 : VS Code

Si VS Code est installé, configurez-le ainsi : 

```sh
git config --global difftool.vscode.cmd 'code --wait --diff $LOCAL $REMOTE'
git config --global diff.tool 'vscode'
git config --global mergetool.vscode.cmd 'code --wait $MERGED'
git config --global mergetool.keepbackup false
git config --global merge.tool 'vscode'
```

#### Choix 2 : DiffMerge

Sinon, nous utiliserons DiffMerge, un outil gratuit, multi-plateforme édité par SourceGear.

Commençons par installer l'outil : https://www.sourcegear.com/diffmerge/downloads.php

Puis nous allons configurer git pour utiliser DiffMerge lorsque nous utiliserons les commandes `git difftool` ou `git mergetool`

```sh
git config --global difftool.diffmerge.cmd "sgdm $LOCAL $REMOTE"
git config --global diff.tool "diffmerge"

git config --global mergetool.diffmerge.cmd "sgdm --merge --result=$MERGED $LOCAL $BASE $REMOTE"
git config --global mergetool.diffmerge.trustexitcode true
git config --global mergetool.keepbackup false
git config --global merge.tool "diffmerge"
```

### Aliases

Vous pouvez mettre en place des alias de commande pour ne pas retaper les mêmes commandes longues et complexes à chaque fois :
* `git config --global alias.lol 'log --oneline --graph --all'`

Celli-ci pourra vous être utile quand vous voudrez regarder le graphe Git.

Lancez cette commande dans un terminal et essayez en lançant `git lol`.

D'autres alias seront proposés dans le kata sur les alias.

### Authentification SSH 

- Consultez https://docs.github.com/fr/authentication/connecting-to-github-with-ssh pour les détails sur l'authentification avec des dépôts sécurisés avec SSH 
- Ou lancez `ssh-keygen` pour générer une paire de clés SSH dans `%USERPROFILE%/.ssh/`:

  `ssh-keygen -t rsa -b 4096 -C "johndoe@example.com"`

  (Ceci génère une paire de clé publique/privée nommées `id_rsa.pub`/`id_rsa`, respectivement)
- La clé **publique** `id_rsa.pub` doit être alors enregistrée sur le serveur de dépôt :
  - Pour GitHub, ce sera dans _Settings_ -> _SSH and GPG keys_
  - Pour BitBucket, ce sera dans _Manage Account_ -> _SSH Keys_
