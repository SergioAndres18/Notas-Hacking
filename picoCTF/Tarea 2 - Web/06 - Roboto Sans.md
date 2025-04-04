## Descripción
The flag is somewhere on this web application not necessarily on the website. Find it. Additional details will be available after launching your challenge instance.

La bandera está en algún lugar de esta aplicación web, no necesariamente en el sitio web. Encuéntrala. Se proporcionarán detalles adicionales después de iniciar tu instancia del desafío.
## Solución
Al inspeccionar la página no encontramos nada especial, la bandera no se encuentra en código ni en la sección HTML, así que inspeccionamos el archivo de `robots.txt`, en dicho archivo encontramos lo siguiente:
```
User-agent *
Disallow: /cgi-bin/
Think you have seen your flag or want to keep looking.

ZmxhZzEudHh0;anMvbXlmaW
anMvbXlmaWxlLnR4dA==
svssshjweuiwl;oiho.bsvdaslejg
Disallow: /wp-admin/
```

Al parecer esta cifrado en base 64, usando `ciberChef` lo desciframos o obtenemos lo siguiente: `js/myfile.txt`, al ingresar a ese archivo en la página obtenemos la bandera:
`picoCTF{Who_D03sN7_L1k5_90B0T5_718c9043}`
## Referencias
https://gchq.github.io/CyberChef