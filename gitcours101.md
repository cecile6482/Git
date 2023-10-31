<!-- 27/10/2023 -->

## apprendre à utiliser git et github

Git est un système de contrôle de version distribué gratuit et open source conçu pour gérer tout, des petits aux grands projets avec rapidité et efficacité. Il permet de suivre, de gérer et d'enregistrer les modifications apportées au code source au fil du temps. C'est un outil de collaboration essentiel pour les développeurs travaillant sur des projets de développement de logiciels. Conçu en 2005 par Linus Torvalds, le créateur de Linux, Git est aujourd'hui utilisé par des millions de développeurs à travers le monde.

Git agit comme un système de suivi des modifications pour les projets, ce qui signifie qu'il enregistre et stocke chaque modification apportée au code source du projet dans un référentiel. Les développeurs peuvent ensuite accéder à ces modifications à tout moment, ce qui permet de revenir à une version antérieure du code source si nécessaire ou de comparer les modifications apportées au code source au fil du temps.
Il permet donc de travailler à plusieurs sur un même projet, de suivre les modifications et de revenir à une version antérieure si nécessaire. Il permet également de travailler sur plusieurs branches en parallèle, ce qui permet de travailler sur plusieurs fonctionnalités en même temps.
Cette approche facilite la gestion de projets complexes et volumineux, car elle permet de suivre les modifications apportées au code source au fil du temps et de revenir à une version antérieure du code source si nécessaire.

Git fonctionne en conservants des instantanés (commit) de projets au fil du temps. Il enregistre les modifications apportées au code source dans un référentiel, puis permet aux développeurs d'accéder à ces instantanés à tout moment. Les développeurs peuvent ainsi revenir à une version antérieure du code source si nécessaire ou comparer les modifications apportées au code source au fil du temps.

Git est souvent utilisé conjointement avec des plateformes d'hébergement de référentiels telles que GitHub et GitLab. Ces plateformes permettent aux développeurs de stocker et de partager des référentiels Git en ligne. Elles offrent également des fonctionnalités de collaboration telles que le suivi des problèmes et les demandes de tirage (pull requests), qui permettent aux développeurs de discuter des modifications apportées au code source avant de les fusionner dans le référentiel principal.

## installation de git

Pour installer git sur votre machine, il suffit de télécharger le logiciel sur le site officiel de git : https://git-scm.com/downloads
Il est compatible avec Windows, Mac et Linux.

## premier pas avec git

Il peut être utilisé via une interface graphique ou en ligne de commande. Nous allons voir les commandes de base en ligne de commande. 
En CLI, toutes les commandes commencent par git. Pour voir la liste des commandes disponibles, il suffit de taper git dans le terminal.

## configuration de git

Avant de commencer à utiliser git, il faut configurer son nom et son email. Pour cela, il faut utiliser les commandes suivantes : 
    git config --global user.name "Votre nom"
    git config --global user.email "Votre email"


### obtenir de l'aide

Pour obtenir de l'aide sur une commande, il suffit de taper git help suivi de la commande. Par exemple, pour obtenir de l'aide sur la commande init, il faut taper git help init.

## initialiser un dépôt (woking directory)

Pour initialiser un dépôt, il faut se placer dans le dossier du projet et taper la commande suivante : git init **dans le repértoire du projet**. Cela va créer un dossier .git qui va contenir toutes les informations relatives au projet. Pour supprimer ce le depot, il suffit de supprimer le dossier .git. Il faudra alors utiliser la commande rm -rf .git pour supprimer le dossier.

## ajouter des fichiers au staging area (index)

Le staging, aussi appellé indexage, est une étape intermédiaire entre le working directory et le dépôt. 
Il permet de préparer les fichiers à être commités. Pour ajouter un fichier au staging area, il faut utiliser la commande git add suivi du nom du fichier. 
Pour ajouter tous les fichiers modifiés au staging area, il faut utiliser la commande git add . (le point signifie tous les fichiers modifiés).

Pour afficher la liste des fichiers modifiés, il faut utiliser la commande git status.

Pour retirer un fichier de la staging area sans annuler les modifications, il faut utiliser la commande git rm --cached suivi du nom du fichier.

## créer un commit (dépôt)

Lorsque mes fichiers sont prêts à être commités, je peux créer un commit. Ce commit agira comme une sauvegarde de mon projet à un instant T. La commande est la suivante : git commit. 
Cela nous ouvre un éditeur de texte pour écrire le message du commit.
Pour créer un commit en une seule commande, il faut utiliser la commande git commit -m "message du commit".


<!-- 30/10/2023  -->

Si j'ajoute l'action -a à la commande git commit, cela va ajouter tous les fichiers modifiés au staging area et créer un commit en une seule commande. 
La commande est la suivante : git commit -a -m "message du commit".

Pour voir l'historique des commits, il faut utiliser la commande git log.

Deux options sont disponibles : 
    -n affiche les n derniers commits. Par exemple, git log -2 affiche les 2 derniers commits.
    -line affiche les commits sur une seule ligne. Par exemple, git log --oneline.

Pour voir les details d'un commit, il faut utiliser la commande git show suivi du hash du commit. Par exemple, git show 2a3d4f.

Enfin, si je souhaite comparer les modifications apportées par un commit, il faut utiliser la commande git diff suivi du hash du commit. Par exemple, git diff 2a3d4f.

## revenir à un commit précédent

Lorsque je dispose de plusieurs commits, je peux revenir à un commit précédent. Pour cela, il faut utiliser la commande git checkout suivi du hash du commit. Par exemple, git checkout 2a3d4f.
Aussi je peux utiliser git reset suivi du hash du commit. Par exemple, git reset 2a3d4f. Cela va supprimer tous les commits après le commit indiqué.

Voilà la différence entre les deux: 
    - git checkout va me permettre de revenir à un commit précédent sans supprimer les commits suivants. 
    - git reset va me permettre de revenir à un commit précédent en supprimant les commits suivants.

Pour revenir au commit actuel, on utilise git switch -.

Utiliser git reset pour revenir à un commit précédent va supprimer les commits suivants. Il existe trois modes de reset : 
    - soft : supprime les commits suivants mais conserve les modifications.
    - mixed : supprime les commits suivants et les modifications.
    - hard : supprime les commits suivants, les modifications et les fichiers.

    Il est important de noter que les commits supprimés ne sont pas supprimés définitivement. Ils sont simplement dé-reférencé, deviennent des commits orphelins et seront supprimés par le garbage collector de git au bout de 30 jours par défaut.

## création d'une étiquette (tag)

La commande git tag permet de créer une étiquette. Par exemple, git tag v1.0.0. Il est possible de créer une étiquette sur un commit précis en ajoutant le hash du commit. Par exemple, git tag v1.0.0 2a3d4f.

Les tags sont des références fixes qui pointent vers un commit précis. Contrairement aux branches, les tags ne sont pas modifiables. Ils sont donc souvent utilisés pour marquer les versions d'un projet ou des points de repère importants.
Attention, un tag ne peut pas contenir d'espace.

   - créer un tag léger
    Pour créer un tag léger, il faut utiliser la commande git tag suivi du nom du tag. Par exemple, git tag v1.0.0. Cela va créer un tag léger sur le commit actuel.

    - créer un tag annoté
    Pour créer un tag annoté, il faut utiliser la commande git tag -a suivi du nom du tag. Par exemple, git tag -a v1.0.0. Cela va créer un tag annoté sur le commit actuel. Cela va nous ouvrir un éditeur de texte pour écrire le message du tag.

    - créer un tag signé
    Pour créer un tag signé, il faut utiliser la commande git tag -s suivi du nom du tag. Par exemple, git tag -s v1.0.0. Cela va créer un tag signé sur le commit actuel. Cela va nous ouvrir un éditeur de texte pour écrire le message du tag.

    - créer un tag sur un commit précis
    Pour créer un tag sur un commit précis, il faut utiliser la commande git tag suivi du nom du tag et du hash du commit. Par exemple, git tag v1.0.0 2a3d4f. Cela va créer un tag léger sur le commit 2a3d4f.

    - créer un tag annoté sur un commit précis

Pour supprimer un tag, il faut utiliser la commande git tag -d suivi du nom du tag. Par exemple, git tag -d v1.0.0.

## créer une branche

Créer des branches dans git est un concept très important. Cela permet de travailler sur plusieurs fonctionnalités, de travailler à plusieurs sur un même projet ou de tester des fonctionnalités sans impacter le code principal.

- créer une nouvelle branche
Pour créer une branche, il faut utiliser la commande git branch suivi du nom de la branche. Par exemple, git branch feature-1. Cela va créer une branche feature-1.

- se déplacer sur une branche
Pour se déplacer sur une branche, il faut utiliser la commande git checkout suivi du nom de la branche. Par exemple, git checkout feature-1. Cela va nous déplacer sur la branche feature-1.
Ou depuis git 2.23, on peut utiliser la commande git checkout -b suivi du nom de la branche. Par exemple, git checkout -b feature-1. Cela va créer la branche feature-1 et nous déplacer dessus.
Depuis git 2.23, on peut utiliser la commande git switch suivi du nom de la branche. Par exemple, git switch feature-1. Cela va nous déplacer sur la branche feature-1.
Git switch est plus intuitif que git checkout car il permet de se déplacer sur une branche ou de créer une branche en une seule commande.
        exemple : git switch -c feature-1

- renommer une branche
Pour renommer une branche, il faut utiliser la commande git branch -m suivi du nouveau nom de la branche. Par exemple, git branch -m feature-1 feature-2. Cela va renommer la branche feature-1 en feature-2.

- supprimer une branche
Pour supprimer une branche, il faut utiliser la commande git branch -d suivi du nom de la branche. Par exemple, git branch -d feature-1. Cela va supprimer la branche feature-1.
Attention: si ma branche n'a pas été fusionnée, git va m'afficher un message d'erreur. Pour forcer la suppression de la branche, il faut utiliser la commande git branch -D suivi du nom de la branche. Par exemple, git branch -D feature-1.

Si je n'ecris que git branch, cela va afficher la liste des branches. La branche sur laquelle je suis est indiquée par une étoile.

Enfin, la commande git diff permet de comparer les modifications apportées par une branche. Par exemple, git diff feature-1.

## Le fichier .gitignore

Ce fichier permet d'ignorer des fichiers ou des dossiers. Pour cela, il suffit de créer un fichier .gitignore à la racine du projet et d'ajouter les fichiers ou dossiers à ignorer. Par exemple, node_modules/.
Il posséde une syntaxe particulière. Pour en savoir plus, consulter la documentation officielle : https://git-scm.com/docs/gitignore

Pour ignorer un fichier ou un dossier déjà suivi par git, il faut simplement ajouter le chemin relatif du fichier ou du dossier dans le fichier .gitignore.

On peut commenter un fichier .gitignore en ajoutant un # au début de la ligne.

Utiliser des patterns dans le fichier .gitignore: 
    - * : permet d'ignorer tous les fichiers et dossiers.
    - ! : permet d'ignorer tous les fichiers et dossiers sauf ceux qui correspondent au pattern.
    - / : permet d'ignorer un dossier.
    - ** : permet d'ignorer tous les fichiers et dossiers dans un dossier.
    - ? : permet d'ignorer un caractère.
    - [] : permet d'ignorer un ensemble de caractères.
    - {} : permet d'ignorer un ensemble de caractères séparés par une virgule.

Une fois le fichier configuré, il faut l'ajouter au staging area et créer un commit. Par exemple, git add .gitignore puis git commit -m "add .gitignore".


