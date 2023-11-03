# FUSION 

## Fusionner les branches (merge/rebase)

Lorsque j'ai fini de travailler sur ma branche, je voudrais souvent appliquer mon travail à la branche principale. (main)
Cette étape est appelée fusion des branches. 
Il existe plusieurs types de fusions possibles : 

## le merge 

Le merge crée un nouveau commit de fusion qui combine les modifications de la branche distante et de votre branche locale. Ce commit de fusion a deux parents : le dernier commit de votre branche et le dernier commit de la branche distante.

Le merge préserve l'historique des commits de manière linéaire et montre clairement quand et d'où proviennent les modifications. 

Il est donc recommandé pour les collaborations sur des projets partagés, car il préserve l'historique des contributions de chaque collaborateur.

**Pour réaliser un merge, il faut se placer sur la branche qui va recevoir les modifications.**

```bash 
git merge 
```

Par exemple, si je veux fusionner ma branche "feature" avec la branche "main", je dois me placer sur la branche "main" et lancer la commande suivante : 

```bash
git switch main
git merge feature
```

Le merge peut rencontrer deux cas de figure :
avec ou sans fast-forward.

S'il y a des conflits entre les deux branches, le merge s'arrête et vous devez résoudre les conflits manuellement.

Par exemple, pour fusionner la branche "feature" avec la branche "main" : 

1- Je me place sur la branche "feature" en utilisant git switch

```bash
git switch feature
```
2- Effectuer le rebase de la branche "feature" sur la branche "main"

```bash
git rebase main
```
Cela réappliquera séquentiellement les commits de la branche "feature" sur la branche "main".

3- Après avoir résolu les conflits et terminé le rebase, on peut maintenant mettre à jour la branche "main" avec les modifications de la branche "feature" en utilisant la commande suivante :

```bash
git switch main
git merge feature
```
Etant donné que la branche "main" est en avance sur la branche "feature", le merge se fera sans fast-forward, ce qui signifie qu'aucun commit de fusion supplémentaire ne sera créé, et la branche "main" pointera sur le même commit que la branche "feature".

## Conclusion: Quelle méthode choisir ?

Le choix entre un merge et un rebase dépends de la manière dont vous voulez voir l'historique de votre projet.
Le merge est généralement recommandé pour les collaborations sur des projets partagés, car il préserve l'historique des contributions de chaque collaborateur. Tandis que le rebase est plutôt recommandé pour les projets personnels, car il permet de garder un historique linéaire et propre.

