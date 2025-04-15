## Descripción
Have you heard of Rust? Fix the syntax errors in this Rust file to print the flag! Download the Rust code [here](https://challenge-files.picoctf.net/c_verbal_sleep/3f0e13f541928f420d9c8c96b06d4dbf7b2fa18b15adbd457108e8c80a1f5883/fixme1.tar.gz).

¿Has oído hablar de Rust? ¡Corrige los errores de sintaxis en este archivo de Rust para imprimir la bandera! Descarga el código de Rust [aquí](https://challenge-files.picoctf.net/c_verbal_sleep/3f0e13f541928f420d9c8c96b06d4dbf7b2fa18b15adbd457108e8c80a1f5883/fixme1.tar.gz).
## Solución
El archivo descargado es un proyecto en Rust el cual es un lenguaje de programación compilado, de propósito general y multiparadigma (aunque no soporta las características de los mismos en su totalidad) que está siendo desarrollado por Fundación Rust.

Usando ubuntu descargamos el archivo con `wget`, con `tar -xvzf fixme1.tar.gz` descomprimimos el proyecto y con `nano src/main.rs` leemos el archivo principal.

El código es el el siguiente:
![[Imagen  01 - Rust fixme 1.png]]
Al intentar ejecutar el programa con `cargo build` y `cargo run` nos indica varios errores, como `;` faltantes o errores en la impresión de variables.

Al solucionar los errores y volver a ejecutar obtenemos la bandera:
`picoCTF{4r3_y0u_4_ru$t4c30n_n0w?}`