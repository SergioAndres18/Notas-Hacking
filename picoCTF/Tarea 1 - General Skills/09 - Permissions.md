## Descripción
Can you read files in the root file? Additional details will be available after launching your challenge instance.

¿Puedes leer archivos en el directorio raíz? Detalles adicionales estarán disponibles después de iniciar tu instancia del desafío.
## Solución
Debemos navegar por las carpetas hasta llegar a la raíz donde se encuentra la carpeta `root` al intentar ingresar a a la carpeta no dice que no tenemos los permisos para hacerlo, por lo que debemos darnos permisos para lograr ver el contenido de `root`, esto lo hacemos con el comando `sudo -l` que nos da permiso para ejecutar el comando `sudo vi /root` que nos permite leer abrir la carpeta `root` con el con el editor de texto `Vi` con privilegios de superusuario y dentro de la carpeta leemos el archivo `flag.txt` donde encontramos la bandera `picoCTF{uS1ng_v1m_3dit0r_89e9cf1a}`