## utiliser git en remote

Pour connecter un repository local à un repository distant tel que Github, il faut suivre les étapes suivantes: 

1- créer un compte sur Github

2- installer git sur votre machine

3- configurer git sur votre machine, en exécutant ces commandes sur le terminal : 
    git config --global user.name "Votre nom"
    git config --global user.email "Votre adresse mail"

4- créer un nouveau repository sur Github
    cliquer sur le bouton "New repository"
    donner un nom à votre repository
    cliquer sur "Create repository"

5- clonez le repository distant sur votre machine
    git clone


## envoyer son projet sur github sans git clone

Pour envoyer un projet sur Github sans git clone, il faut suivre les étapes suivantes:
il faut utiliser la commande git remote pour ajouter un dépôt distant et git fetch pour récupérer les modifications effectuées sur le dépôt distant.

1- créer un nouveau référentiel sur Github

2- dans le dossier local, initialiser le référentiel local
    git init

3- ajouter le référentiel distant à votre référentiel local
    git remote add nom_perso_distant <URL du référentiel distant>

    remplacer nom_perso par le nom de votre référentiel distant
    git remote add origin <URL du référentiel distant>

    Si vous avez fait une erreur en tapant l'URL du référentiel distant, vous pouvez la modifier avec la commande suivante: 
    git remote set-url origin <URL du référentiel distant>

4- vérifier que le référentiel distant a été ajouté à votre référentiel local
    git remote -v

    Cela affichera les référentiels des urls distants associés à votre référentiel local.

5- récupérer les modifications effectuées sur le référentiel distant avec la commande suivante:
    git fetch nom_perso_distant

    remplacer nom_perso par le nom de votre référentiel distant
    git fetch origin

    Cela récupérera toutes les branches du référentiel distant, mais ne fusionnera pas automatiquement avec votre référentiel local. 

6- ensuite, pour travailler avec les modifications du référentiel distant, vous pouvez créer une branche locale qui suit la branche distante avec la commande suivante:
    git checkout -b nom_branche nom_perso_distant/nom_branche

Vous pouvez maintenant travailler sur votre branche locale et envoyer vos modifications sur le référentiel distant sans git clone.

## le git pull

Pour récupérer les modifications effectuées sur le référentiel distant et les fusionner avec votre référentiel local, vous pouvez utiliser la commande git pull.

git pull branche_distant branche_locale
    ex: git pull origin main 


Lorsque vous exécutez un git pull, ces étapes se succédent : 

1- git fetch récupère les modifications effectuées sur le référentiel distant et les enregistre dans votre référentiel local. 

2- fusion automatique: git fusionne les modifications de la branche distante avec votre branche locale. Si Git rencontre des conflits, il vous demandera de les résoudre manuellement.

3- finalisation: une fois que la fusion (ou rebase) est terminée, Git crée un commit de fusion qui combine les modifications de la branche distante et de votre branche locale.