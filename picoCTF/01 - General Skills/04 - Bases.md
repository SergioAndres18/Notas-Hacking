## Descripción
What does this `bDNhcm5fdGgzX3IwcDM1` mean? I think it has something to do with bases.
¿Qué significa esto `bDNhcm5fdGgzX3IwcDM1`? Creo que tiene algo que ver con bases.
## Solución
La cadena esta en base 64, para saber su significado se podría hacer lo siguiente:
- Puede usar herramientas web para convertir la cadena.
- En Linux se puede decodificar desde el BASH usando el comando 
```
$ echo "CADENA" | base64 -d
```

Se uso Ubuntu para hacer la decodificación, la solución es la siguiente:
```
sergio_so@DESKTOP-F40822T:~$ echo "bDNhcm5fdGgzX3IwcDM1" | base64 -d
l3arn_th3_r0p35
```
La solución es `picoCTF{l3arn_th3_r0p35}`
## Notas adicionales

## Referencias
https://www.base64decode.org/es/
https://rm-rf.es/codificar-y-descodificar-base64-desde-bash/