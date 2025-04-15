#### Description

Cookie Monster has hidden his top-secret cookie recipe somewhere on his website. As an aspiring cookie detective, your mission is to uncover this delectable secret. Can you outsmart Cookie Monster and find the hidden recipe?You can access the Cookie Monster [here](http://verbal-sleep.picoctf.net:56571/) and good luck

#### Hints 
- Sometimes, the most important information is hidden in plain sight. Have you checked all parts of the webpage?
- Cookies aren't just for eating - they're also used in web technologies!
- Web browsers often have tools that can help you inspect various aspects of a webpage, including things you can't see directly.

## Solución
-Tener una extensión para ver las cookies
-Ingersamos cualquier usuario y contraseña
-Copiamos la cookie que nos salga y lo decodificamos de base 64

```
En cyberchef
Input: cGljb0NURntjMDBrMWVfbTBuc3Rlcl9sMHZlc19jMDBraWVzXzk2RjU4REFCfQ%3D%3D
From Base64
Output:picoCTF{c00k1e_m0nster_l0ves_c00kies_96F58DAB}
ÃÜ

```

https://gchq.github.io/CyberChef/
