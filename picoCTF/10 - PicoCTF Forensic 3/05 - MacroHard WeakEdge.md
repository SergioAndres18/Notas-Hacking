## Descripción
I've hidden a flag in this file. Can you find it? [Forensics is fun.pptm](https://mercury.picoctf.net/static/3944a59474f9f676942282c50b9c3675/Forensics is fun.pptm)

He ocultado una bandera en este archivo. ¿Puedes encontrarla? La informática forense es divertida.pptm
## Solución
Al abrir el archivo con un lector de archivos `.pptm` con `PowerPoint` o `LibreOficce` no encontramos nada en la presentación.  Así que intentaremos ver en los archivos del documento, con el comando `unzip 'Forensics is fun.pptm'` desempaquetamos el archivo.

Como resultado obtenemos varios archivos y carpetas, buscando encontramos un archivo llamado `hidden.txt` en la dirección `Carpeta\ppt\slideMasters`, al leerlo obtenemos lo siguiente `Z m x h Z z o g c G l j b 0 N U R n t E M W R f d V 9 r b j B 3 X 3 B w d H N f c l 9 6 M X A 1 f Q`, con el comando `echo "Z m x h Z z o g c G l j b 0 N U R n t E M W R f d V 9 r b j B 3 X 3 B w d H N f c l 9 6 M X A 1 f Q" | tr -d " " | base64 -d` podemos desencriptarlo.

Con `tr -d " "` eliminamos los espacios entre los caracteres y con  `base64 -d` desencriptamos la cadena y obtenemos la bandera `picoCTF{D1d_u_kn0w_ppts_r_z1p5}`