#### Description

The Multiverse is within your grasp! Unfortunately, the server that contains the secrets of the multiverse is in a universe where keyboards only have numbers and (most) symbols.

Additional details will be available after launching your challenge instance.

#### Hints 
- Where can you get some letters?

## Solución
-Tener una extensión para ver las cookies
-Ingersamos cualquier usuario y contraseña
-Copiamos la cookie que nos salga y lo decodificamos de base 64

```
En base a la pagina, comenzamos a agragar simobolo para encontrar nuestro flag
https://tldp.org/LDP/GNU-Linux-Tools-Summary/html/x11655.htm

SansAlpha$ /*/???[!_]64 */????.*
cmV0dXJuIDAgcGljb0NURns3aDE1X211MTcxdjNyNTNfMTVfbTRkbjM1NV9iMGQ1ZTg1NX0=

como resultado nos da una serie de numeros que sopondremos que estan en base 64, lo rtansformamos con el cyberchef

Input: cmV0dXJuIDAgcGljb0NURns3aDE1X211MTcxdjNyNTNfMTVfbTRkbjM1NV9iMGQ1ZTg1NX0=
from base 64
Output: return 0 picoCTF{7h15_mu171v3r53_15_m4dn355_b0d5e855}

```

https://gchq.github.io/CyberChef/
https://tldp.org/LDP/GNU-Linux-Tools-Summary/html/x11655.htm
