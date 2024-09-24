# Sommaire

  ## 1. [Processus et filtre](#process)
  ## 2. [Gestion des users et groupe](#gestion)
  ## 3. [package manager](#package)
  ## 4. [Configuration](#config)
  ## 5. [Partitions](#Partitions)
  ## 6. 
   

# Processus en Crabe <a name="process">   

**PID**  
non-spécifique au term dans lequel on l'a lancé  
`$ ps`  
`$ pstree`  

**Jobs**  
spécifique au term dans lequel on l'a lancé  
pour parler des jobs il faut mettre % avant le numéro de jobs   
`$ jobs`  

**Kill/Stop/...**  
gère l'état des processus
`$ kill -s <signal> <PID/%jobs>...`  

__liste signaux:__  
    > * KILL : force kill  
    > * STOP : stop  
    > * TERM : kill gentil trop choupi  
    > * CONT : relance un processus précédemment stoppé  
    > * sinon y a des numéros mais flm  

**bg/fg**  
fout en arrière plan (bg/'&') ou en avant plans (fg) un processus  
`$ fg/bg <PID/%jobs>...`  


## Redirections (entrées/sorties) de Zinzin mon pote à la compote  
**nom term**
`$ tty`

**n (déscripteur) {0, 1, 2}:**
    * 0 : entrée standard
    * 1 : sortie standard
    * 2 : sortie erreur

**afficher le contenu d'un fichier dans un autre term**
`$ cat <fichier> 1><term>`

**afficher une erreur dans un autre term**
`$ cat <fichier> 2><term>`

**écraser/créer un fichier en redirigeant un texte d'un autre fichier**
`$ cat <fichier> 1><fichier>`

**append le contenu d'un fichier dans un autre fichier**
`$ cat <fichier> 1>><fichier>`

**rediriger la sortie standard sur la sortie d’erreur**
`$ ???`


## Filtres  

### tr
> * [:alpha:] : [a-zA-Z]
> * [:alnum:] : [a-zA-Z0-9]
> * [:digit:] : [0-9]
> * [:blank:] : space
> * [:graph:] : tout sauf espace
> * [:print:] : tout
> * [:xdigit:] : [A-F0-9]
> * [:lower:]/[:upper:] : min/maj

**full maj**
`$ cat <ficher> | tr [:lower:] [:lower:]`

**suppr avec tr**
`$ cat <ficher> | tr -d <elem>`

### cut

> * """borne non-comprise"""
> * -<borne> : garde tout ce qu'il y a avant la borne
> * <borne>- : garde tout ce qu'il y a après la borne
> * <borne1>-<borne2> : garde ce qu'il y a entre les bornes
> * -<borne1>,<borne2>- : garde ce qu'il y a autour des bornes
> * """borne non-comprise"""

> * -b : nb bytes / ensemble de bytes
> * -c : nb char / ensembles de char
> * -d : détermine un char en délimiteur
> * -f : détermine le field (nb de fois qu'on va passer le delim)(s'utilise avec -d)
> * --complement : prend tout sauf ce qui est select par le cut (cut avec selection inversé)


**cut un elem spécifique**
`$ cat <fichier> | cut -c <borne1>-<borne2>`

**retirer un elem spécifique**
`$ cat <fichier> | cut -c -<borne1>,<borne2>-`

**cut du début jusqu'a un elem spécifique**
`$ cat <fichier> | cut -c -<borne1>`

**cut d'un elem spécifique jusqu'à la fin**
`$ cat <fichier> | cut -c <borne2>-`


# Gestion des users et groupe <a name="gestion">

> les infos users sont stockés dans /etc/passwd
> les passwd chiffrés sont stockés dans /etc/shadow
> les infos des groups dont dans /etc/group

**add sudoers (add user au grp sudo)**

`$ usermod -aG sudo user`  

**La création d'utilisateur**  
`adduser (sur debian et ubuntu) - créer un utilisateur sur la machine` 

**changer le mdp user**  
`$ passwd <user>`  
  
**donner le droit d'exec tt les cmd**  
__dans /etc/sudoers__  
`<user>  ALL=(ALL:ALL) ALL`  

**suppr un user**  
`$ deluser <user> --remove-home`  

**La création d'un groupe**  
`sudo addgroup - créer un groupe`  

**ajout d'un utilisateur dans un groupe**  
pour exemple, quand on créer l'utilisateur tata  
`adduser tata`  

**changer le groupe d'un fichier**  
`$ chown <:group> <file>` 

**changer le propriétaire d'un fichier**  
`$ chown <user> <file>` 



# package manager <a name="package">

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



# Configuration  <a name="config">

**changer la langue sys**  
`$ dpkg-reconfigure locales`  

**changer la timezone**  
`$ dpkg-reconfigure tzdata`  

**changer le profils de touche (azerty/qwerty)**  
`$ dpkg-reconfigure keyboard-configuration`  



# Partitions <a name="Partitions">

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

 


# Dual boot <a name="dual">

  

# Fonctionnalité systeme
  


# Xorg -> wayland (mais I3 c'est mieux)

  

# gestion kernel

  

# manual install (nsm jveux pas le faire)
