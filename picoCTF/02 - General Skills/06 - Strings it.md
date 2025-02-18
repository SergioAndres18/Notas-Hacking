## Descripción
Can you find the flag in [file](https://jupiter.challenges.picoctf.org/static/5bd86036f013ac3b9c958499adf3e2e2/strings) without running it?
¿Puedes encontrar la bandera en el archivo sin ejecutarlo?
## Solución
Usando el comando `strings strings | grep -i "pico"` podemos buscar la bandera dentro del archivo sin ejecutarlo.
```
La respuesta es:
picoCTF{5tRIng5_1T_827aee91}
```
## Referencias
https://linux.die.net/man/1/strings