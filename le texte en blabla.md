# BlipBloup  





## Gestion utilisateur et groupe de bot a la compote 

**La création d'utilisateur**  

`adduser (sur debian et ubuntu) - créer un utilisateur sur la machine`  


**changer le mdp user**
`$ passwd toto`  


**add sudoers**
usermod -aG sudo user <!-- ajoute user au groupe sudo --->

> les infos users sont stockés dans /etc/passwd
> les passwd chiffrés sont stockés dans /etc/shadow

**La création d'un groupe**  
`sudo addgroup - créer un groupe`  

**ajout d'un utilisateur dans un groupe**  
pour exemple, quand on créer l'utilisateur tata  
`adduser tata`  

pour l'ajouter dans le groupe existant ou crée recemment l'on doit faire :
`usermod -aG <groupe> <utilisateur>`  

par exemple :  
`usermod -aG bidule tata`  

pour etre sur que tata est bien dans le groupe desiré, inserer cette ligne de commande :  

`groups <utilisateur>`  





## package manager


## Partitions


## Dual boot


## Fonctionnalité sys


## Xorg -> wayland (mais I3 c'est mieux)


## gestion kernel


## manual install (nsm jveux pas le faire)
