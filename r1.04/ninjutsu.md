# BlipBloup  

## Substitution de variables + cmd

> * ${...} : ouvre un nouveau shell dans lequel il execute la cmd (ou qqch comme ça) 

**kill des processus**

__marche po__
`$ kill %${jobs | grep xeyes | tail -n 1 | cut -c 2}`   (jobs pas dans le bon term)

__marche du feu de dieu__
`$ TEMP=jobs | grep xeyes | tail -n 1 | cut -c 2`       (jobs dans le bon term)
`$ kill %${TEMP}`                                       (pas obligé les brackets la)
ou
`$ TEMP=ps | grep xeyes | tail -n 1 | cut -d ' ' -f 2`
`$ kill %$TEMP`


## Jokers

## Scripts bash

**première ligne**
`#!/bin/bash`

> * $nb : arg présent sur la ligne de cmd
> * $#  : nb arg(s)
> * $* ou $@  : tout les arg(s)
> * pas oublier le chmod


**rediriger la sortie vers le néant absolu**

... 2>/dev/null 1>&2    (redirige tout vers le fichier /dev/null qui fait return rien)

**blip bloup**