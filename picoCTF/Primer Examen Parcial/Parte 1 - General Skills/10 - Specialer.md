# Specialer

## Description

Reception of Special has been cool to say the least. That's why we made an exclusive version of Special, called Secure Comprehensive Interface for Affecting Linux Empirically Rad, or just 'Specialer'. With Specialer, we really tried to remove the distractions from using a shell. Yes, we took out spell checker because of everybody's complaining. But we think you will be excited about our new, reduced feature set for keeping you focused on what needs it the most. Please start an instance to test your very own copy of Specialer.

`ssh -p 65259 ctf-player@saturn.picoctf.net`. The password is `483e80d4`

## Hints

* What programs do you have access to?

## Solución

Primero iniciamos nuestra instancia, una vez echo esto, nos dirigimos a nuestra terminal de ubuntu o de igual manera se puede realizar en el webshell del picoCTF.

primero ingresamos nuestra instancia, en este caso es: `ssh -p 65259 ctf-player@saturn.picoctf.net`, después escribimos **yes**.
Enseguida nos pide nuestra contraseña, la cual nos la da nuestra instancia y en este caso es: `483e80d4`.

Después aplicamos un `echo */*` para observar que archivos de textos contiene y sus nombres los cuales son los siguientes:
* abra/cadabra.txt 
* abra/cadaniel.txt 
* ala/kazam.txt 
* ala/mode.txt 
* sim/city.txt 
* sim/salabim.txt

Una vez identificados escribimos el comando `echo "$(<abracadabra/.txt)"` con cada archivo de texto que nos aparecieron anteriormente hasta que nos salga nuestra respectiva flag.

En este caso la flag apareció en este .txt `echo "$(<ala/kazam.txt)"`.

## Terminal de ejemplo:

```
jazmin@DESKTOP-1CBQJ6D:~$ ssh -p 65259 ctf-player@saturn.picoctf.net
The authenticity of host '[saturn.picoctf.net]:65259 ([13.59.203.175]:65259)' can't be established.
ECDSA key fingerprint is SHA256:dJtvF/J5LfkJcePCA5aEPg1zZbM6yb37NnsNhGVyygI.
Are you sure you want to continue connecting (yes/no/[fingerprint])? yes
Warning: Permanently added '[saturn.picoctf.net]:65259,[13.59.203.175]:65259' (ECDSA) to the list of known hosts.
ctf-player@saturn.picoctf.net's password:
Specialer$ pwd
/home/ctf-player
Specialer$ echo *
abra ala sim
Specialer$ echo */*
abra/cadabra.txt abra/cadaniel.txt ala/kazam.txt ala/mode.txt sim/city.txt sim/salabim.txt
Specialer$ echo "$(<abracadabra/.txt)"
-bash: abracadabra/.txt: No such file or directory

Specialer$ echo "$(<abra/cadabra.txt)"
Nothing up my sleeve!
Specialer$ echo "$(<abra/cadaniel.txt)"
Yes, I did it! I really did it! I'm a true wizard!
Specialer$ echo "$(<ala/kazam.txt)"
return 0 picoCTF{y0u_d0n7_4ppr3c1473_wh47_w3r3_d01ng_h3r3_d5ef8b71}
jazmin@DESKTOP-1CBQJ6D:~$
```

### Respuesta: picoCTF{y0u_d0n7_4ppr3c1473_wh47_w3r3_d01ng_h3r3_d5ef8b71}
