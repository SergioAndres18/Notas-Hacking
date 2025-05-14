## Descripción
Can you win in a convincing manner against this chess bot? He won't go easy on you! You can find the challenge [here](http://verbal-sleep.picoctf.net:51452/).

¿Puedes ganar de manera convincente contra este bot de ajedrez? ¡No te lo pondrá fácil! Puedes encontrar el desafío aquí.
## Solución
Al ingresar a la página vemos un tablero de ajedrez, en la página de picoCTF nos dice que ganemos de manera convincente, pero el bot es muy bueno y es muy difícil ganarle, por lo que debemos revisar el código de la página para ver si podemos encontrar otra manera de ganar.

Podemos encontrar la función `sendMessage` a la cual se le envia `mate` o `eval` junto a un valor numérico. 
![[Imagen 04 - WebSockFish.png]]

Si utilizamos el la consola del inspector del navegador, en este caso Firefox, y usamos la función `sendMessage` y probamos distintos valores podemos encontrar la bandera, en este caso con `eval -100000` nos muestra la bandera: `picoCTF{c1i3nt_s1d3_w3b_s0ck3t5_b820bcc2}`

![[Imagen 05 - WebSockFish.png]]


---
Notas relacionadas:
- [[01 - Bookmarklet]]
- [[02 - Cookie Monster Secret Recipe]]
- [[03 - head-dump]]
- [[04 - n0s4n1ty 1]]
- [[05 - SSTI1]]
- [[06 - findme]]
- [[07 - Java Code Analysis!]]
- [[08 - SQL Direct]]
- [[09 - SSTI2]]
- [[10 - WebSockFish]]
- [[01 - FANTASY CTF]]
---