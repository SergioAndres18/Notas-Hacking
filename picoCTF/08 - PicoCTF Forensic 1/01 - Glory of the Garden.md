## Descripción
This [garden](https://jupiter.challenges.picoctf.org/static/4153422e18d40363e7ffc7e15a108683/garden.jpg) contains more than it seems.
Este jardín contiene más de lo que parece.
## Solución
El comando `strings -n18 garden.jpg` en Ubuntu busca y muestra todas las cadenas de texto legible que tengan al menos 18 caracteres consecutivos dentro del archivo binario `garden.jpg`; esto permite detectar fragmentos de texto ocultos o metadatos incrustados en la imagen, como comentarios, nombres de software, o incluso datos escondidos intencionalmente.
```
sergio_so@DESKTOP-F40822T:~/Garden$ strings -n18 garden.jpg

Copyright (c) 1998 Hewlett-Packard Company
IEC http://www.iec.ch
IEC http://www.iec.ch
.IEC 61966-2.1 Default RGB colour space - sRGB
.IEC 61966-2.1 Default RGB colour space - sRGB
,Reference Viewing Condition in IEC61966-2.1
,Reference Viewing Condition in IEC61966-2.1
%&'()*456789:CDEFGHIJSTUVWXYZcdefghijstuvwxyz
&'()*56789:CDEFGHIJSTUVWXYZcdefghijstuvwxyz
Here is a flag "picoCTF{more_than_m33ts_the_3y33dd2eEF5}"
```
Usando el comando anterior podemos encontrar la bandera.


---
Notas relacionadas:
- [[01 - Glory of the Garden]]
- [[02 - So Meta]]
- [[03 - shark on wire 1]]
- [[04 - extensions]]
- [[05 - What Lies Within]]
---