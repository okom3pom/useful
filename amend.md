Faire : `git rebase -i ma-branch~n` 

n correspond au nombre de commit à affichier.


La commande 

`$ git rebase -i ma-branch~3`

Retoune la liste suivant:

```
pick e499d89 Delete CNAME
pick 0c39034 Better README
pick f7fde4a Change the commit message but push the same commit.
```


Commands:
 - p, pick = use commit
 - r, reword = use commit, but edit the commit message
 - e, edit = use commit, but stop for amending
 - s, squash = use commit, but meld into previous commit
 - f, fixup = like "squash", but discard this commit's log message
 - x, exec = run command (the rest of the line) using shell

**Si vous supprimer une ligne le commit sera supprimé**


Dans notre cas on veut changer le message des commit on remplace pick par reword.

```
 pick e499d89 Delete CNAME
 reword 0c39034 Better README
 reword f7fde4a Change the commit message but push the same commit.
```

On enregistre : CTRL + 0 

On va alors devoir rentrer le nouveau message des commits

On enregistre

`$ git push --force`
