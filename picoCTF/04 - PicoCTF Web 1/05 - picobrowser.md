## Descripción
This website can be rendered only by **picobrowser**, go and catch the flag! `https://jupiter.challenges.picoctf.org/problem/26704/` ([link](https://jupiter.challenges.picoctf.org/problem/26704/)) or http://jupiter.challenges.picoctf.org:26704
## Solución
Al ingresar a la página debemos dar clic en un botón llamado flag, al hacerlo nos dice que solo se puede hacer desde el navegador `picobrowser`, para hacernos pasar por este navegador debemos inspeccionar la página y en la parte de red volver a dar clic en el botón para ver las cabeceras de solicitud y respuesta, con el navegador Firefox podemos modificar la cabecera de respuesta para hacernos pasar por el navegador picobrowser, al hacerlo podemos ver la bandera:
```
picoCTF{p1c0_s3cr3t_ag3nt_e9b160d0}
```
## Notas adicionales

## Referencias
