## Descripción
A group of underground hackers might be using this legit site to communicate. Use your forensic techniques to uncover their message
Additional details will be available after launching your challenge instance.
Try it [here](http://standard-pizzas.picoctf.net:50042/)!

Un grupo de hackers clandestinos podría estar utilizando este sitio legítimo para comunicarse. Usa tus técnicas forenses para descubrir su mensaje.
Detalles adicionales estarán disponibles después de iniciar tu instancia del reto.
Intenta [aquí](http://standard-pizzas.picoctf.net:50042/)!
## Solución
En la pagina podemos ver muchas banderas de países, pero revisándolas vemos la bandera de `Upanzi, Republic The` el cual esta mal escrito y no existe ese país, por lo que esto puede ser de los hackers.
Descargamos la imagen de la bandera y usamos la herramienta `stepic` de la siguiente manera `stepic -d -i upz.png` lo cual nos dará la bandera `picoCTF{fl4g_h45_fl4g9a81822b}`
