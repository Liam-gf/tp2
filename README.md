**Nom :** Girard--Fourneaux Liam

**Groupe :** Equipe 01

**Année :** 2025

**IUT Le Havre - Cours GIT**

# Compte-rendu TP2 Introduction GIT



## 1. Créer un compte GitHub


Il faut aller sur GitHub et cliquer sur *sign up*.

Ensuite il faut renplir les champs pour crée son compte.


## 2. Ajouter une nouvelle clé SSH à votre compte GitHub


Il faut copier la clé ssh de votre machine, pour l'afficher il faut faire la commande :

*cat ~/.ssh/`Nom de votre clé`.pub*

Il faut seulement prendre la clé publique, la clé privée (sans .pub) ne dois jamais être partagée.


Si il n'existe pas de clé publique/privée dans le répertoire ssh il faut en générer une avec la 
commande :

*ssh-keygen*

Après avoir copier votre clé ssh publique, il faut aller sur GitHub, cliquer sur le **profil**, aller 
dans **settings**, ensuite dans **SSH and GPG keys**, et cliquer sur **New SSH key**.

Après cela, il faut remplir le titre et collé la clé copier auparavant dans le cadre *key* et cliqué 
sur **Add SSH key*.


## 3 Pousser un dépôt existant depuis la ligne de commande


3 commandes vont être importantes afin de gérer un répertoire distant :

- **git remote :** afin de crée un lien entre notre dépôt local et notre dépôt distant
- **git push :** pour mettre à jour le dépôt distant à partir de la dernière version du dépôt local.
- **git pull :** pour mettre à jour le dépôt local à partir de la dernière version du dépôt distant.


Afin de crée un dépôt distant il faut aller en haut à droite de l'écran et cliqué sur 
**New repository**. Cela ouvre un formulaire. Dans ce formulaire on peut mettre un nom de dépôt, 
une description, choisir de le mettre en publique ou en privé.

Ces étapes permettent de crée un dépôt distant sous la forme d'un lien :

*https://github.com/`Votre nom`/`Le nom du dépôt`.git*


Ensuite il faut choisir l'option SSH. Cela va crée un lien sous la forme :

*git@github.com:`Votre nom`/`le nom du dépôt`.git*


Pour vérifié que un dépôt local n'est relier à aucuns dépôt distant il faut que la commande suivante 
ne renvoie rien :

*git remote -v*

Pour lier un dépôt local à un dépôt distant il faut faire :

*git remote add origin git@github.com:`Votre nom`/`le nom du dépôt`.git*

Les versions des différents commit sont stockées dans une branch, soit **master** soit **main**.
Pour connaître cela il faut faire la commande :

*git branch*


Pour crée le lien il faut faire la commande :

*git push -u origin master*

Après cela, on peut voir sur le lien du projet que les fichiers de notre dépôt distant sont les mêmes 
que le dépôt local.


## 4 Séquence de travail avec un dépôt distant


Pour récupérer la version la plus récente du dépôt distant il faut faire la commande :

*git pull*

Pour voir les modifications il faut faire : 

*git log*

Quand notre dépôt local est dans sa dernière version, pour modifier le dépôt distant il faut faire :

*git push*


### Exercice

On fait : 

- *git pull*
- *git log*

On modifie le fichier `Cryptomonnaie.java`.

- *git status*
- *git add `src\Cryptomonnaie.java`*
- *git commit -m "Ajout de getters et setters"*
- *git push*

On voit maintenant que le dépôt distant contient les modifications apportées à `Cryptomonnaie.java`.


## 5 Cloner un dépôt distant sur notre machine locale


Pour cela il faut crée un nouveau repository comme vu précédement.

Copié le lien : git@github.com:`Votre nom`/`le nom du dépôt`.git

Et faire la commande : git clone git@github.com:`Votre nom`/`le nom du dépôt`.git

Il y a désormais un dossier tp2.


Ensuite on copie colle à la main les fichier existant dans tp1 dans le tp2. Après cela on *git add* 
et *git commit* tout les fichiers.

Lorsque tout est fini, on *git push* afin d'avoir nos fichiers sur le dépôt distant.
