# olalefichiai

## hd
> **od de wish**
> - partie de gauche : offset
> - milieu : contenu (en hex, oct, ...)
> - partie de droite : contenu en char

`$ hd <fichier>`

## od
`$ od -A o -t oS -w16 <fichier>`    // <od par default>

### OPTIONS
> - -t : type/format (o : octal; x1 : hexa; ...)[SIZE]. z après pour display les char printable dans la partie de droite
> - -N : select que les N premier char 
> - --endian=a{big|little} 

## hexedit
> hexedit - view and edit files in hexadecimal or in ASCII
> parties comme sur od

### CMD
> - F2 : save 
> - Ctrl+X : save and exit  
> - Ctrl+C : exit without saving
> - Ctrl+u : undo all
> - Ctrl+u : search forward
> - Ctrl+u : search backward

### EDIT
**écrit et ça edit**
> - Tab : toggle hex/ascii (partie milieu et droite)
