## Descripción
How well can you perfom basic binary operations? Additional details will be available after launching your challenge instance.

¿Qué tan bien puedes realizar operaciones binarias básicas? Detalles adicionales estarán disponibles después de iniciar tu instancia del desafío.
## Solución
Al conectarnos a la maquina virtual con el comando `nc titan.picoctf.net 55904` nos hara preguntas de operaciones con números binarios tales como: 
```
Binary Number 1: 00010011
Binary Number 2: 01001100

Question 1/6:
Operation 1: '<<'
Perform a left shift of Binary Number 1 by 1 bits.
Enter the binary result: 00100110
Correct!

Question 2/6:
Operation 2: '|'
Perform the operation on Binary Number 1&2.
Enter the binary result: 01011111
Correct!

Question 3/6:
Operation 3: '>>'
Perform a right shift of Binary Number 2 by 1 bits .
Enter the binary result: 00100110
Correct!

Question 4/6:
Operation 4: '&'
Perform the operation on Binary Number 1&2.
Enter the binary result: 00000000
Correct!

Question 5/6:
Operation 5: '+'
Perform the operation on Binary Number 1&2.
Enter the binary result: 01011111
Correct!

Question 6/6:
Operation 6: '*'
Perform the operation on Binary Number 1&2.
Enter the binary result: 10110100100
Correct!

Enter the results of the last operation in hexadecimal: 5A4
```

Al acabar nos muestra la bandera `picoCTF{b1tw^3se_0p3eR@tI0n_su33essFuL_d6f8047e}`
