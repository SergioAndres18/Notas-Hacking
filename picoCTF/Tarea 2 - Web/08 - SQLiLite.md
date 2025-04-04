## Descripción
¿Puedes iniciar sesión en este sitio web? Se proporcionarán detalles adicionales después de iniciar tu instancia del desafío.
## Solución
La página nos pide registrarnos, al hacerlo nos dice `Login failed`, además de eso nos muestra lo siguiente:
```
username: 
password: 
SQL query: SELECT * FROM users WHERE name='' AND password=''
```

Lo que pertenece a una solicitud de SQL, por lo que podemos intentar realizar una inyección SQL, la cadena `admin' or 1=1 -- -` es un ejemplo clásico de una inyección SQL (SQLi), específicamente diseñada para explotar vulnerabilidades en aplicaciones que no sanitizan correctamente las entradas de los usuarios en consultas SQL.
Al ingresar la cadena en la zona de usuario junto a cualquier contraseña nos muestra lo siguiente:
![[Imagen 01 - SQLiLite.png]]
Si inspeccionamos el código de la página podemos ver la bandera:
`picoCTF{L00k5_l1k3_y0u_solv3d_it_9b0a4e21}`