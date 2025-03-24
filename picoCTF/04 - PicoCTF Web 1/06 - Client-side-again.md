## Descripción
Can you break into this super secure portal? `https://jupiter.challenges.picoctf.org/problem/60786/` ([link](https://jupiter.challenges.picoctf.org/problem/60786/)) or http://jupiter.challenges.picoctf.org:60786
## Solución
Para poder encontrar la bandera, inspeccionamos el código de la página, en el encontraremos un script en java script que se encuentra ofuscado (escrito de tal manera que al ser humano se le complique comprenderlo), para acomodarlo se usó chatGPT quedando de la siguiente manera: 
```javascript
// Variables desofuscadas
const phrases = ['f49bf}', '_again_e', 'this', 'Password Verified', 'Incorrect password', 'getElementById', 'value', 'substring', 'picoCTF{', 'not_this'];

// Función para verificar contraseña
function verify() {
  const checkpass = document.getElementById('pass').value;
  const split = 4;

  // Comprobaciones de la contraseña
  if (checkpass.substring(0, split * 2) === 'picoCTF{') {
    if (checkpass.substring(7, 9) === '{n') {
      if (checkpass.substring(split * 2, split * 4) === 'not_this') {
        if (checkpass.substring(3, 6) === 'oCT') {
          if (checkpass.substring(split * 6, split * 8) === 'f49bf}') {
            if (checkpass.substring(6, 11) === 'F{not') {
              if (checkpass.substring(split * 4, split * 6) === '_again_e') {
                if (checkpass.substring(12, 16) === 'this') {
                  alert('Password Verified');
                  return;
                }
              }
            }
          }
        }
      }
    }
  }
  
  alert('Incorrect password');
}

```
Analizando el código podemos encontrar el orden de los segmentos pertenecientes a la bandera quedando de la siguiente manera `picoCTF{not_this_again_ef49bf}`
## Notas adicionales
Existen otras herramientas web para des ofuscar código.
## Referencias
https://chatgpt.com/