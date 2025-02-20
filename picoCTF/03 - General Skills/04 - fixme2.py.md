## Descripción
Fix the syntax error in this Python script to print the flag.

Arregla el error de sintaxis en el script de Python para imprimir la bandera.
## Solución
- Podemos intentar ejecutar el script con `python fixme2.py`, al hacer esto fallará y nos dirá que existe un error, nos muestra en que línea del código existe y que tipo de error es. 
- También se puede usar editor de código con verificador de errores en tiempo real como Visual Studio Code.
El error dentro del código es en la línea 22, consiste en un error de sintaxis dentro de la condición del if, en vez de usar `==` tiene `=`, haciendo incorrecta la comparación.
```
La bandera es:
picoCTF{3qu4l1ty_n0t_4551gnm3nt_e8814d03}
```