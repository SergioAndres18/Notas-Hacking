## Descripción
Kishor Balan tipped us off that the following code may need inspection: `https://jupiter.challenges.picoctf.org/problem/44924/` ([link](https://jupiter.challenges.picoctf.org/problem/44924/)) or http://jupiter.challenges.picoctf.org:44924

## Solución
Ingresar a la página dada e inspeccionar el código fuente de la página, hay secciones en distintos lenguajes y encada una de estas están las partes de la bandera, dentro del mismo encontramos los comentarios:
```html
<!-- Html is neat. Anyways have 1/3 of the flag: picoCTF{tru3_d3 -->
```
```css
/* You need CSS to make pretty pages. Here's part 2/3 of the flag: t3ct1ve_0r_ju5t */
```
```js
/* Javascript sure is neat. Anyways part 3/3 of the flag: _lucky?f10be399} */
```

## Notas adicionales

## Referencias