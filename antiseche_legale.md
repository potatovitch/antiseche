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


## Filtres  

### tr  
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


## Combinaisons de filtres    
