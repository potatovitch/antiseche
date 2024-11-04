# BlipBloup  

## bases

### tr

> * **considéré comme un seul car (mettre les quotes autours)**
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

**tr plusieurs char**
> remplace 'a' par 'e' et 'e' par 'a'
`$ cat tuyaux | tr ea ae`


### cut

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


### grep

`$ cat <fichier> | grep <char/string>`

> * -v : inverse
> * -i : case insensitive
> * -c : count
> * -o : only matching


### sort
`$ cat <fichier> | sort -d`

`$ cat <fichier> | sort -k <indice+1>`

> * -d : alphanumeric sort
> * -k : keydef


## Combinaisons de filtres

## filtres sur gros fichiers

## SED (aaaahhhhh)

**afficher une ligne**
`$ cat <fichier> | sed -n '<LIGNES><LETTRES><OPTION>'`
`$ cat <fichier> | sed -n '3p'`

**suppr une ligne**
`$ cat <fichier> | sed '<LIGNES>d'`

**remplacer m1 par m2**
`cat tuyaux | sed '<LIGNES>s/<m1>/<m2>/g'`
> * g : global (ne s'arrete pas à la première occ)

**affiche une ligne sur deux**
`$ cat tuyaux | sed -n '1~2p'`

> * -n : affiche ce qui est select et pas tout en plus de ce qui est select

**LIGNES**
> * <borne1><elt><borne2>...
> * ';' : select ligne
> * ',' : select ligne(s) entres
> * '~' : pas des ligne(s) select

**LETTRES** 
> * p : afficher lignes
> * d : delete
> * s : ajoute/remplace

**OPTION**
> * s(uniquement)/<m1>/<m2>/g

**avec OPTION s**
> * s/^/<chaine>/ : met <chaine> en début de ligne ('^' cible le debut de ligne)
> * s/$/<chaine>/ : met <chaine> en fin de ligne ('$' cible le debut de ligne)
> * !s/.../.../   : select les lignes non vides ???
> * s/^$/.../     : select les lignes vides     ???