## Descripción
In RSA, a small `e` value can be problematic, but what about `N`? Can you decrypt this? [values](https://mercury.picoctf.net/static/b9ddda080c56fb421bf30409bec3460d/values)

En RSA, un valor pequeño de `e` puede ser problemático, pero ¿qué hay de `N`? ¿Puedes descifrar esto? [valores](https://mercury.picoctf.net/static/b9ddda080c56fb421bf30409bec3460d/values)
## Solución
Leemos el archivo con `cat values` veremos los siguiente:
```
sergio_so@DESKTOP-F40822T:~/values$ cat values
Decrypt my super sick RSA:
c: 964354128913912393938480857590969826308054462950561875638492039363373779803642185
n: 1584586296183412107468474423529992275940096154074798537916936609523894209759157543
e: 65537
```

Usamos el modo interactivo de Python para desencriptar el mensaje, para crear p y q usamos una herramienta online para factorizar el valor de n, quedando de la siguiente manera: 
```Python
sergio_so@DESKTOP-F40822T:~/values$ python3
Python 3.10.12 (main, Feb  4 2025, 14:57:36) [GCC 11.4.0] on linux
Type "help", "copyright", "credits" or "license" for more information.
>>> c = 964354128913912393938480857590969826308054462950561875638492039363373779803642185
>>> n = 1584586296183412107468474423529992275940096154074798537916936609523894209759157543
>>> e = 65537
>>> p = 2434792384523484381583634042478415057961
>>> q = 650809615742055581459820253356987396346063
>>> p * q
1584586296183412107468474423529992275940096154074798537916936609523894209759157543
>>> tn = (p - 1) * (q - 1)
>>> d = pow (e, -1, tn)
>>> m = pow(c, d, n)
>>> m
13016382529449106065927291425342535437996222135352905256639684640304028661985917
>>> bytes.fromhex(hex(m)[2:])
b'picoCTF{sma11_N_n0_g0od_73918962}'
>>>
```
## Referencias
https://factordb.com/