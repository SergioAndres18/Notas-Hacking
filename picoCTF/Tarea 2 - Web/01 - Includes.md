## Descripción
Can you get the flag? Additional details will be available after launching your challenge instance. Go to this [website](http://saturn.picoctf.net:50254/) and see what you can discover.

¿Puedes obtener la bandera? Los detalles adicionales estarán disponibles después de iniciar tu instancia de desafío. Ve a este [sitio web](http://saturn.picoctf.net:50254/) y mira qué puedes descubrir.
## Solución
Al entrar en la página vemos un texto que habla de la directiva `include` que hace que el contenido de un segundo archivo se inserte en el archivo original.

Si inspeccionamos el código del archivo vemos que incluye dos archivos externos en `CSS` y `JS`. Si ingresamos a ellos podemos encontrar la bandera en los comentarios.
`picoCTF{1nclu51v17y_1of2_f7w_2of2_df589022}`