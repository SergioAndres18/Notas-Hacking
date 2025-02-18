## Descripción
Unzip this archive and find the file named 'uber-secret.txt'
Descomprime este archivo y encuentra el archivo llamado 'uber-secret.txt'
## Solución
Usando los comandos unzip y find en Linux podemos descomprimir y buscar el archivo.
1. Primero debemos abrir una terminal y ubicarnos en la dirección donde se encuentra el archivo files.zip.
2. Una vez localizado debemos usar el comando `unzip files.zip`.
3. Para buscar el archivo se usa el comando `find . -name "uber-secret.txt"`.
4. Nos arrojara la ubicación del archivo, la copiamos y con el comando `cd 'direccion_del_archivo'`nos ubicamos en la dirección.
5. Con el comando `cat uber-secret.txt`podemos ver lo que contiene el archivo.
```
La respuesta es:
picoCTF{f1nd_15_f457_ab443fd1}
```
## Notas adicionales
Se podría usar un buscador de archivos, como el Windows o el de algún programa como RAR.
## Referencias
https://help.dreamhost.com/hc/es/articles/115002768331-Comandos-UNIX-Descomprimir-archivos
https://www.ionos.mx/digitalguide/servidores/configuracion/comando-linux-find/