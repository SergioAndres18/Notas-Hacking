## Descripción
Decode this [message](https://jupiter.challenges.picoctf.org/static/14393e18d98fedbaedbc28896d7ef31a/message.wav) from the moon.

Decodifica este mensaje de la luna.
## Solución
La codificación SSTV (Slow Scan Television, o Televisión de Barrido Lento) es un sistema de transmisión de imágenes mediante ondas de radio, donde la información visual se convierte en señales de audio y se transmite a través de las ondas de radio. En este proceso, las imágenes se escanean línea por línea, y cada píxel se representa como una frecuencia de sonido.

Sabiendo lo anterior podemos saber intentar usar un decodificador SSTV, existen herramientas en línea para este propósito, en este caso usamos un repositorio de github en ubuntu, usaremos los siguientes comandos: 
```bash
git clone https://github.com/colaclanth/sstv.git
cd sstv
python setup.py install

#Volvemos a la carpeta donde tengamos el archivo .wav
sstv -d message.wav -o result.png
```

Una vez hecha la decodificación se habrá creado una imagen `.png`, al abrirla podemos encontrar la bandera.
![[Imagen 01 - m00nwalk.png]]
## Notas adicionales

## Referencias
https://github.com/colaclanth/sstv