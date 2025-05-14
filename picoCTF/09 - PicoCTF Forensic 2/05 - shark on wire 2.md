## Descripción
We found this [packet capture](https://jupiter.challenges.picoctf.org/static/b506393b6f9d53b94011df000c534759/capture.pcap). Recover the flag that was pilfered from the network.

Encontramos esta captura de paquetes. Recupera la bandera que fue robada de la red.
## Solución
Al descargar la captura y abrirla con `WireShark` y seguir la conversación de UDP no encontramos nada. Pero si buscamos `udp.dsport == 22` encontramos una serie de paquetes UDP con puertos de origen en el rango de los 5000, si obtenemos los últimos dos valores de cada puerto obtenemos un carácter, si convertimos todos los puertos obtendremos la bandera, para ello creamos un script en Python que reste 5000 a cada paquete y el resultado lo convierta a carácter.

```python
from scapy.all import *

packets = rdpcap('capture.pcap')
flag = ''
for p in packets:
        if UDP in p and p[UDP].dport == 22:
                if p[UDP].sport > 5000:
                        flag += chr(p[UDP].sport - 5000)

print(flag)
```

Al ejecutar el script obtenemos la bandera `picoCTF{p1LLf3r3d_data_v1a_st3g0}`

---
Notas relacionadas:
- [[01 - m00nwalk]]
- [[02 - WhitePages]]
- [[03 - c0rrupt]]
- [[04 - like1000]]
- [[05 - shark on wire 2]]
---