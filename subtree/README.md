# Git Katas: Subtree

Subtree est un moyen d'incorporer l'historique d'un autre dépôt git dans votre dépôt en fusionnant les commits. Il permet également de pousser des correctifs vers le dépôt du subtree. On pourra donc synchroniser dans les deux sens le contenu de ce dépôt.

Cette fonctionnalité est utile quand on souhaite partager un répertoire entre plusieurs dépôts.

## Mise en place

1. Lancez le script `source setup.sh` sous Linux ou `.\setup.ps1` dans PowerShell sous Windows

## Étapes

### Ajout du subtree

Au départ, vous avez 2 dépôts dans le répertoire `exercise`:

- `product` : dépôt contenant l'historique du produit
- `component`: dépôt contenant l'historique du composant

Exercice

1. Consultez l'historique du composant
1. Consultez l'historique du produit
1. Ajoutez le composant en tant que *remote* avec la commande : `git remote add component ../component/.git`
1. Vérifiez les remote avec `git remote -v`
1. Ajoutez l'historique du composant dans le dépôt dans un sous-répertoire `component` qui sera placé sous le répertoire `product` avec la commande : `git subtree add --prefix component component master`.
1. Expliquez ce qui s'est passé. Consultez l'historique des deux dépôts avec `git log --graph --oneline --all` et expliquez l'historique commun et le dernier commit de `product`.

### Récupérer des commits depuis le subtree

Les opérations précédentes ont au final créé un répertoire `component` dans le dépôt `product` en tant que subtree, on nomme également ce type de répertoire un `prefix`. Nous allons maintenant modifier le composant et intégrer les modifications dans le produit.

1. Dans le dépôt `component` faites une modification et un commit
1. Dans le dépôt `product` récupérez les modifications avec la commande : `git subtree pull --prefix component component master`
1. Expliquez ce qui s'est passé. Consultez l'historique des deux dépôts avec `git log --graph --oneline --all` et expliquez l'historique commun et le dernier commit de `product`.

### Pousser des commits vers le subtree

Dans l'autre sens, on veut maintenant faire de modifications dans le subtree et les pousser vers le dépôt `component. Dans l'exercice nous pousserons vers une branche.

1. Dans le dépôt `product`, placez vous dans le répertoire `component`, faites un changement et un commit.
1. Poussez le commit avec la commande : `git subtree push --prefix component component patch`
1. Expliquez ce qui s'est passé. Consultez l'historique des deux dépôts avec `git log --graph --oneline --all` et expliquez l'historique commun et le dernier commit de `product`.
1. Pourquoi pousser vers une branche ?
1. Et si vous n'étiez pas propriétaire du dépôt `component`, comment feriez-vous ?

## Commandes utiles

- `git log --graph --oneline --all`
- `git subtree add --prefix component component master`
- `git remote add component ../component/.git`
- `git subtree push --prefix <prefix/directory> <repo> <branch>`

## Ressources

Quelques liens utiles :

- <https://github.com/git/git/blob/master/contrib/subtree/git-subtree.txt>
- <https://blog.developer.atlassian.com/the-power-of-git-subtree/>