# BlipBloup  

## Processus en Crabe  

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
    > * 0 : entrée standard
    > * 1 : sortie standard
    > * 2 : sortie erreur

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


## tee

> écrit le contenu dans un fichier et dans la sortie standard

**écrit dans un fichier et compte le nombre de lignes**
`$ cat <fichier> | tee <fichier> | wc -l`

**afficher dans un term et compter nb lignes dans un autre**
`$ cat <fichier> | tee /dev/pts/? | wc -l`

**afficher les lignes contenant un mot et les lignes dans un autre**
`$ cat <fichier> | grep <mot> | cut -c 1- | tee /dev/pts/? | wc -l 1>/dev/pts/?` 
