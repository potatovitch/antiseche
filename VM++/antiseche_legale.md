# BlipBloup  

## Gestion des users

> les infos users sont stockés dans /etc/passwd
> les passwd chiffrés sont stockés dans /etc/shadow
> les infos des groups dont dans /etc/group

**add sudoers (add user au grp sudo)**

`$ usermod -aG sudo user`  

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

**changer la langue sys**  
`$ dpkg-reconfigure locales`  

**changer la timezone**  
`$ dpkg-reconfigure tzdata`  

**changer le profils de touche (azerty/qwerty)**  
`$ dpkg-reconfigure keyboard-configuration`  


## Partitions

**faites un instantané**  


> souvent la partition utilisable linux est au format ext4
> ??? swap pour la ram ???
> jsp
> jsp
> le disk est monté sur /dev/sda?

**afficher les partitions**  
`$ fdisk -l`  

**place free d'un disk**  
`$ df -ah`  

**info sur les partitions**  
`$ fdisk -x`  

**entrer dans fdisk**  
`$ fdisk <disk>`                    <!-- disk : disk sur lequel on veut faire la partition --->  

**créer une partition**   
__dans fdisk__    
`$ d`                               <!-- suppr toute les partition existantes--->  
`$ n`                               <!-- ajouter une nouvelle partition --->  
`$ p`                               <!-- partition primaire --->  
`$ <enter>`                         <!-- appuyer sur entrer --->  
`$ +<taille><unit>`                 <!-- ex : $ +11G --->  

**modifier une partition**  
__dans fdisk__  
`$ t`                               <!-- change le type de la partition --->  
`$ L`                               <!-- lister tout les codes --->  
`$ 83`                              <!-- choisit linux dans le code HEX listé précedemment--->  
`$ w`                               <!-- quitte fdisk --->  
`$ mkfs.ext4 -b 4096 /dev/sda?`     <!-- ext4 : format de la partition; blocks de 4096 octets; /dev/sda1 : disk sur lesuel on monte la partition --->  

**monter la partition dans un dir**  



## Dual boot


## Fonctionnalité sys


## Xorg -> wayland (mais I3 c'est mieux)


## gestion kernel


## manual install (nsm jveux pas le faire)

