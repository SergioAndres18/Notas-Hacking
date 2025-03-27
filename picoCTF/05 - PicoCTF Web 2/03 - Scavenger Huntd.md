## Descripción
There is some interesting information hidden around this site [http://mercury.picoctf.net:27278/](http://mercury.picoctf.net:27278/). Can you find it?

Hay información interesante oculta en este sitio [http://mercury.picoctf.net:27278/](http://mercury.picoctf.net:27278/). ¿Puedes encontrarla?
## Solución
En la páginas se menciona que la misma está escrita en HTML, CSS y JS. La bandera se encuentra dividida en partes y escondida en el código y archivos de la página. Las ubicaciones son las siguientes:
1. En el código fuente de la página podemos encontrar la primera parte de la bandera, además de entrar a las secciones escritas en CSS y JS.
	![[Imagen 01 - Scavenger Hunt.png]]
	![[Imagen 02 - Scavenger Hunt.png]]
2. En la parte escrita en CSS se encuentra la segunda parte de la bandera.
	![[Imagen 03 - Scavenger Hunt.png]]
3. En la parte escrita en JS, nos dice `How can I keep Google from indexing my website? (¿Cómo puedo evitar que Google indexe mi sitio web?)`, para evitar que Google indexe un sitio web, podemos utilizar un archivo robots.txt, así que si ingresamos al archivo de robots, añadiendo robots.txt al url de la página (`http://mercury.picoctf.net:27278/robots.txt`) obtenemos la siguiente parte de la bandera.
	![[Imagen 04 - Scavenger Hunt.png]]
4. En el anterior punto nos indica que la página se encuentra en un servidor apache (software de servidor web de código abierto que actúa como un intermediario entre el navegador del usuario y el servidor donde están alojados los archivos del sitio web), podemos acceder a un archivo de configuración (.htaccess) utilizado por servidores web Apache, esto lo hacemos añadiendo .htaccess al url de la página (http://mercury.picoct[[]]f.net:27278/.htaccess).
```
	# Part 4: 3s_2_lO0k
	# I love making websites on my Mac, I can Store a lot of information there.
```
5.  En el anterior punto nos indica que la página se creó en una maquina MAC y que guarda información ahí, si subes una carpeta desde una computadora macOS a un servidor web, es posible que los archivos `.DS_Store`(el cual es un archivo oculto creado automáticamente por **macOS** en cada carpeta) se suban accidentalmente junto con el resto de los archivos del sitio. Como en los casos anteriores podemos acceder al mismo añadiendo `.DS_Store`al url de la página (http://mercury.picoctf.net:27278/.DS_Store). Así obtenemos la última parte de la bandera.
```
	Congrats! You completed the scavenger hunt. Part 5: _a69684fd}
```

Si juntamos todas las partes obtenemos la bandera:
`picoCTF{th4ts_4_l0t_0f_pl4c3s_2_lO0k_a69684fd}`