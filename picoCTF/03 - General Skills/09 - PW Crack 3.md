## Descripción
Can you crack the password to get the flag? Download the password checker [here](https://artifacts.picoctf.net/c/17/level3.py) and you'll need the encrypted [flag](https://artifacts.picoctf.net/c/17/level3.flag.txt.enc) and the [hash](https://artifacts.picoctf.net/c/17/level3.hash.bin) in the same directory too. There are 7 potential passwords with 1 being correct. You can find these by examining the password checker script.

¿Puedes descifrar la contraseña para obtener la bandera? Descarga el verificador de contraseñas aquí y necesitarás la bandera encriptada y el hash en el mismo directorio.

Hay 7 posibles contraseñas, pero solo 1 es correcta. Puedes encontrarlas examinando el script del verificador de contraseñas.
## Solución
Al ejecutar script de Python con el comando `python level3.py` nos pedirá una contraseña. Para conocerla debemos abrir el script con un editor de texto o de código y buscar dentro la contraseña.

Podemos eliminar o comentarizar la parte del código donde se verifica la contraseña y desencriptar directamente usando las contraseñas hasta que salga la correcta. Quedando el código así:
```
import hashlib 

### THIS FUNCTION WILL NOT HELP YOU FIND THE FLAG --LT ########################

def str_xor(secret, key):

    #extend key to secret length

    new_key = key

    i = 0

    while len(new_key) < len(secret):

        new_key = new_key + key[i]

        i = (i + 1) % len(key)        

    return "".join([chr(ord(secret_c) ^ ord(new_key_c)) for (secret_c,new_key_c) in zip(secret,new_key)])

###############################################################################

  

flag_enc = open('level3.flag.txt.enc', 'rb').read()

# The strings below are 7 possibilities for the correct password.

#   (Only 1 is correct)

pos_pw_list = ["f09e", "4dcf", "87ab", "dba8", "752e", "3961", "f159"]

  

for pw in pos_pw_list:

    try:

        decryption = str_xor(flag_enc.decode(), pw)

        if "picoCTF{" in decryption:  # Si el resultado parece válido, lo mostramos

            print("Flag encontrada:", decryption)

            break

    except:

        continue
```

La bandera es `picoCTF{m45h_fl1ng1ng_cd6ed2eb}`.
