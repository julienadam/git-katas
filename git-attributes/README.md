# Git Kata: Le fichier Git attributes

Nous allons travailler avec le fichier [`.gitattributes`](https://www.git-scm.com/docs/gitattributes)
dans ce kata. Dans ce fichier, vous pouvez spécifier comment git doit gérer certains types de fichiers. Par exemple, quel type de délimiteur de ligne utiliser pour un fichier texte (CRLF ou LF), ou quel outil de diff utiliser pour certains fichiers binaires.

Les exercices suivants ne sont valables que sur GNU/Linux ou Mac.
are for GNU/Linux platforms and Mac.

## Mise en place

1. Lancez le script `source setup.sh` sous Linux ou `.\setup.ps1` dans PowerShell sous Windows

## Étapes

1. Créez un fichier `.gitattributes` avec le contenu suivant:

    `*.txt      text=auto eol=lf working-tree-encoding=UTF-8`

2. Lancez `git add file1.txt .gitattributes`, vous  allez voir le message suivant :

    `warning: CRLF will be replaced by LF in file1.txt.`

3. Modifiez `eol` en `auto` ou `crlf`. Expliquez pourquoi une seule des options produit le message ci-dessus.

4. Certains fichiers doivent avoir des délimiteurs de ligne DOS (CRLF) pour fonctionner. Typiquement les fichier .bat. on utilisera alors ce type de configuration :
   `*.bat      text=auto eol=crlf`

   Un problème similaire, en miroir, se pose lorsqu'on travaille avec des scripts Linux contenant un *shebang* qui définit l'interpréteur.
   Si le fichier utilise des délimiteurs CRLF, le script ne s'exécutera pas car le CR sera compris comme un caractère et non pas comme une fin de ligne.

5. Git est principalement prévu pour les fichiers texte mais peut tout à fait gérer des fichiers binaires et il est possible de définir une commande de diff spécifique pour certains fichiers.

   Dans cet exemple, on va utiliser `exiftool` pour afficher et comparer les meta-donnés de fichiers d'image. Vous aurez besoin de cet outil pour réaliser l'exercice. Vous pouvez l'installer simplement avec `apt install exiftool` ou `brew install exiftool`.

   Une fois installé, on va configurer un driver de diff dans la configuration git pour utiliser `exiftool` afin de "convertir" l'image en texte qui pourra être comparé.

   Ajoutez les lignes suivantes dans votre `~/.gitconfig` ou dans le fichier local `.git/config`.

   ```shell
   [diff "useexif"]
   textconv = exiftool
   cachetextconv = true
   ```

   Il ne reste plus qu'à définir ce "driver" pour les fichiers de type `PNG`. Ajoutez la ligne suivante au fichier `.gitattributes` créé en début d'exercice :

   ```shell
   *.png diff=useexif
   ```

6. On peut maintenant tester l'ensemble

   Vous pouvez utiliser l'image mario.png située dans le même répertoire que ce README. ( Mario png tiré de <https://www.freepngimg.com/download/mario/20698-7-mario-transparent-background.png> )

   ![Mario large](mario.png)

   Copiez l'image vers le répertoire de l'exercice avec `cp ../mario.png .`, utilisez `git add` pour mettre l'image en staging.

   `git diff --staged` va maintenant afficher un diff en comparant la version en staging avec la version précédente (inexistante donc /dev/null).

   Faites un commit.

7. Pour vraiment voir l'intérêt de l'outil, remplacez l'image par une autre image et comparez les deux versions. Par exemple en utilisant l'image `mario-small.png`.

   ![Mario small](mario-small.png)

   Exécutez `cp ../mario-small.png ./mario.png` pour écraser la version actuelle avec la version *small*. Git va correctement détecter un changement.

   Lancez git diff, il va maintenant comparer le contenu des méta-données EXIF et nous permettra de voir sous forme textuelle les différences dans les attributes de l'image

## Commandes utiles

- `file file1.txt` (on GNU/Linux and Mac)
- `git add`
- `git status`
- `iconv` pour convertir entre plusieurs formats d'encodage
