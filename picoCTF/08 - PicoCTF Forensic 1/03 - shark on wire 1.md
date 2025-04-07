## Descripción
We found this [packet capture](https://jupiter.challenges.picoctf.org/static/483e50268fe7e015c49caf51a69063d0/capture.pcap). Recover the flag.
Encontramos este packet_capture. Recupera la bandera.
## Solución
Usando el programa `WireShark` podemos abrir el paquete de captura con el comando `wireshark capture.pcap`, siguendo la conversación entre los paquetes udp podemos encontrar la bandera
![[Imagen 01 - shark in wire 1.png]]