# Squash commit.

Tout d’abord, il faut récupérer le sha1 du commit précédant celui dans lequel on va squasher, puis on l’utilise pour lancer la commande :

`git rebase -i fbde9fd9c14c9f449f9461b6d3c17c92923b97f0`

Ou 5 ici égale aux nombre de commit 

`git rebase -i HEAD~5`

On entre alors en mode interactif (on utilise l’éditeur de git). Les commits sont affichés du plus ancien au plus récent.

```
pick  fbde9fd   Add Readme.md
pick  70aaed5   Update Readme
pick  ccf2779   Update Readme again
pick  8c706b5   Update Readme again and again
```

Le premier commit correspond à celui de base, celui que l’on souhaite conserver ; on laisse donc l’instruction “pick” devant. On souhaite squasher tous les commits suivants, on met donc l’instruction “squash” devant. (vous pouvez aussi utiliser l’alias “s” à la place de “squash”)

On obtient alors :

```
pick    fbde9fd Add Readme.md
squash  70aaed5 Update Readme
squash  ccf2779 Update Readme again
squash  8c706b5 Update Readme again and again
```

On enregistre dans GIT, ensuite on modifie les messages des commits et on enregistre.

Pour finir : 

`git push --force`
