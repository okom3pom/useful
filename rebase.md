# Rebase a PR

On ajoute l'upstream : 

`git remote add upstream https://github.com/PrestaShop/PrestaShop.git`

On récupère l'état de l'upstream

`git fetch upstream`

Sur la branche de la PR :

`git rebase upstream/develop`

Si il y a des conflits, on corrige et on fait

`git rebase --continue`

Si on sent qu'on a peur de faire trop de merdes :

`git rebase --abort`

Hormis le dernier cas, on force push (vu qu'on a changé l'historique de git

`git push --force`
