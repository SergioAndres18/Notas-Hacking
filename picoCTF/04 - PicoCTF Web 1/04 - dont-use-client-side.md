## Descripción
Can you break into this super secure portal? `https://jupiter.challenges.picoctf.org/problem/37821/` ([link](https://jupiter.challenges.picoctf.org/problem/37821/)) or http://jupiter.challenges.picoctf.org:37821
## Solución
Al ingresar a la página debemos de ingresar una contraseña, como no la sabemos intentamos inspeccionar el código, al revisarlo podemos ver una serie de ifs con los cuales se verifica la contraseña, al analizarlos podemos obtener la bandera:
`picoCTF{no_clients_plz_1a3c89}`