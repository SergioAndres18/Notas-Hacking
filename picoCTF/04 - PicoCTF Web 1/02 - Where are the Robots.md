## Descripción
Can you find the robots? `https://jupiter.challenges.picoctf.org/problem/36474/` ([link](https://jupiter.challenges.picoctf.org/problem/36474/)) or http://jupiter.challenges.picoctf.org:36474
## Solución
Al ingresar en la página dada por PicoCTF veremos en el sitio no podemos interactuar con nada, por lo que debemos encontrar la manera de ingresar al contenido.

El archivo `robots.txt` es un archivo de texto que los administradores de sitios web colocan en el servidor para dar instrucciones a los bots (también llamados rastreadores o spiders) de los motores de búsqueda.

Cuando se agrega `/robots.txt` a la URL de un sitio web (por ejemplo, `https://www.ejemplo.com/robots.txt`), puedes ver las reglas que indican a los bots qué partes del sitio pueden o no pueden rastrear e indexar, con esto podemos ver que en la página se le dice a los robots que deshabiliten la parte `/477ce.html`de la página.

Al agregar `/477ce.html`al url podremos ver la bandera:
`picoCTF{ca1cu1at1ng_Mach1n3s_477ce}`
## Referencias
https://es.wikipedia.org/wiki/Est%C3%A1ndar_de_exclusi%C3%B3n_de_robots