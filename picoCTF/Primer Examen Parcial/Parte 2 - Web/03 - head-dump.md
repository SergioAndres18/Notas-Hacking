#### Description

Welcome to the challenge! In this challenge, you will explore a web application and find an endpoint that exposes a file containing a hidden flag.The application is a simple blog website where you can read articles about various topics, including an article about API Documentation. Your goal is to explore the application and find the endpoint that generates files holding the server’s memory, where a secret flag is hidden.

Additional details will be available after launching your challenge instance.
#### Hints 

1 - Explore backend development with us
2 - The head was dumped.

#### Solución

Entramos en la pagina seguido de esto en la seccion John Doe damos clik al link azul de #API Documentation.

Despues en "Diagnosing" lo probamos y descargamos el documento que nos genera, y dentro de este se encuentre la bandera, solo usamon un ctrl + f para buscar "picoCTF" y listo.

REFERENCIAS:

https://www.youtube.com/watch?v=SzWctEfVdGk

````
picoCTF{Pat!3nt_15_Th3_K3y_63fa652c}
``` 