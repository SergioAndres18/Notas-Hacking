## Descripción
Can you make sense of this file? Download the file [here](https://artifacts.picoctf.net/c/473/enc_flag).
¿Puedes darle sentido a este archivo?
## Solución
Al abrir con un editor de texto vemos que tiene el siguiente texto
```
VmpGU1EyRXlUWGxTYmxKVVYwZFNWbGxyV21GV1JteDBUbFpPYWxKdFVsaFpWVlUxWVZaS1ZWWnVh
RmRXZWtab1dWWmtSMk5yTlZWWApiVVpUVm10d1VWZFdVa2RpYlZaWFZtNVdVZ3BpU0VKeldWUkNk
MlZXVlhoWGJYQk9VbFJXU0ZkcVRuTldaM0JZVWpGS2VWWkdaSGRXCk1sWnpWV3hhVm1KRk5XOVVW
VkpEVGxaYVdFMVhSbHBWV0VKVVZGWm9RMlZzV2tWUmJFNVNDbUpXV25wWmExSmhWMGRHZEdWRlZs
aGkKYlRrelZERldUMkpzUWxWTlJYTkxDZz09Cg==
```
El cual esta codificado en base64, al usar un decodificador online nos vuelve a dar otro texto en base64, este también lo decodificamos. Este proceso lo tenemos que repetir varias veces hasta que nos la la bandera correcta.
```
La respues es:
picoCTF{base64_n3st3d_dic0d!n8_d0wnl04d3d_dfe803c6}
```
## Notas adicionales
Se podría crear un programa en Python que decodifique el texto en bucle hasta que encuentre la cadena pico CTF. 
## Referencias
https://base64.guru/converter/decode/ascii