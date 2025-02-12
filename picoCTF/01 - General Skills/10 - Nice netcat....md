## Descripción
There is a nice program that you can talk to by using this command in a shell: `$ nc mercury.picoctf.net 21135`, but it doesn't speak English...
Hay un programa interesante con el que puedes comunicarte usando este comando en una terminal: `$ nc mercury.picoctf.net 21135`, pero no habla ingles...
## Solución
Al conectarnos mediante netcat nos arroja los siguientes números:
112, 105, 99, 111, 67, 84, 70, 123, 103, 48, 48, 100, 95, 107, 49, 116, 116, 121, 33, 95, 110, 49, 99, 51, 95, 107, 49, 116, 116, 121, 33, 95, 97, 102, 100, 53, 102, 100, 97, 52, 125, 10.
Para que hable ingles debemos convertir los número a ASCII, se puede usar un convertidor online.
```
La respuesta es:
picoCTF{g00d_k1tty!_n1c3_k1tty!_afd5fda4}
```
## Referencias
https://www.prepostseo.com/tool/decimal-to-ascii