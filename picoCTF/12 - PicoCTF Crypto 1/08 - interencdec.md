## Descripción
Can you get the real meaning from this file. Download the file [here](https://artifacts.picoctf.net/c_titan/111/enc_flag).

¿Puedes obtener el significado real de este archivo? Descarga el archivo [aquí](https://artifacts.picoctf.net/c_titan/111/enc_flag).
## Solución
Descargamos el archivo y con `cat enc_flag` y obtenemos:
`YidkM0JxZGtwQlRYdHFhR3g2YUhsZmF6TnFlVGwzWVROclh6ZzVNR3N5TXpjNWZRPT0nCg==`

Parece estar en base 64, usamos `echo "YidkM0JxZGtwQlRYdHFhR3g2YUhsZmF6TnFlVGwzWVROclh6ZzVNR3N5TXpjNWZRPT0nCg==" | base64 -d`

Como resultado obtenemos `d3BqdkpBTXtqaGx6aHlfazNqeTl3YTNrXzg5MGsyMzc5fQ==` el cual nuevamente esta en base 64, así que volvemos a usar el comando `echo "d3BqdkpBTXtqaGx6aHlfazNqeTl3YTNrXzg5MGsyMzc5fQ==" | base64 -d`

Como resultado obtenemos `wpjvJAM{jhlzhy_k3jy9wa3k_890k2379}` el cual parece que sus caracteres tienen una rotación, usamos `CyberChef` con la herramienta `ROT13` y lo rotamos 19 veces, como resultado obtenemos la bandera `picoCTF{caesar_d3cr9pt3d_890d2379}`

## Referencias
https://gchq.github.io/CyberChef/
---
Notas relacionadas:
- [[01 - The numbers]]
- [[02 - 13]]
- [[03 - caesar]]
- [[04 - Easy 1]]
- [[05 - la cifra de]]
- [[06 - Tapping]]
- [[07 - waves over lambda]]
- [[08 - interencdec]]
---