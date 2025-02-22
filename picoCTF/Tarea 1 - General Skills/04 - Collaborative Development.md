## Descripción
My team has been working very hard on new features for our flag printing program! I wonder how they'll work together? You can download the challenge files here:
- [challenge.zip](https://artifacts.picoctf.net/c_titan/69/challenge.zip)

¡Mi equipo ha estado trabajando arduamente en nuevas funciones para nuestro programa de impresión de banderas! Me pregunto cómo funcionarán juntas. Puedes descargar los archivos del desafío aquí:
- [challenge.zip](https://artifacts.picoctf.net/c_titan/69/challenge.zip)
## Solución
Para ver los branch que son ramas o versiones paralelas de un proyecto usamos el comando `git branch -a`, nos aparecen tres versiones y para cambiar a alguna de las ramas usamos el comando `git checkout feature/nombre` y para ver el contenido del archivo `flag.py` de la rama actual usamos el comando `cat flag.py` 

El contenido de cada rama es:
Rama 1:
```
print("Printing the flag...")
print("picoCTF{t3@mw0rk_", end='')
```
Rama 2:
```
print("Printing the flag...")
print("m@k3s_th3_dr3@m_", end='')
```
Rama 3:
```
print("Printing the flag...")
print("w0rk_e4b79efb}")
```

Al unir las tres ramas obtenemos la bandera `picoCTF{t3@mw0rk_m@k3s_th3_dr3@m_w0rk_e4b79efb}`
