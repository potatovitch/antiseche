# BlipBloup  

**add sudoers**

usermod -aG sudo user <!-- ajoute user au groupe sudo --->


## Gestion des users
> les infos users sont stockés dans /etc/passwd
> les passwd chiffrés sont stockés dans /etc/shadow
> les infos des groups dont dans /etc/group

**changer le mdp user**
`$ passwd <user>`

**changer le propriétaire d'un fichier**
`$ chown <user> <file>`

**changer le groupe d'un fichier**
`$ chown <:group> <file>`

**donner le droit d'exec tt les cmd**
__dans /etc/sudoers__
`<user>  ALL=(ALL:ALL) ALL`

**suppr un user**
`$ deluser <user> --remove-home`

## package manager

> ne pas oublier installer les lib des packages manager

**installer un packet avec apt-get**
`$ apt-get install <packet>`

**installer un packet avec snap**
`$ snap install <packet>`

**installer un packet avec homebrew**
`$ brew install <packet>`

> sinon tu prend la commande pour install dans la doc de l'app que t'installe

**supprimmer un packet**
`$ apt-get remove <packet>`

**purge(full remove) un packet**
`$ apt-get purge <packet>`

> pour le reste tu regarde la doc de ton PM j'ai pas que ça à faire


## Config


## Partitions


## Dual boot


## Fonctionnalité sys


## Xorg -> wayland (mais I3 c'est mieux)


## gestion kernel


## manual install (nsm jveux pas le faire)


