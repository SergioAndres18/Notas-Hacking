## Descripción
Find the flag being held on this server to get ahead of the competition [http://mercury.picoctf.net:53554/](http://mercury.picoctf.net:53554/)

Encuentra la bandera que se encuentra en este servidor para adelantarte a la competencia: [http://mercury.picoctf.net:53554/](http://mercury.picoctf.net:53554/)
## Solución
Usando Ubuntu, si le mandamos una solicitud `GET`a la página nos regresa
```html
<!doctype html>
<html>
<head>
    <title>Red</title>
    <link rel="stylesheet" type="text/css" href="//maxcdn.bootstrapcdn.com/bootstrap/3.3.5/css/bootstrap.min.css">
        <style>body {background-color: red;}</style>
</head>
        <body>
                <div class="container">
                        <div class="row">
                                <div class="col-md-6">
                                        <div class="panel panel-primary" style="margin-top:50px">
                                                <div class="panel-heading">
                                                        <h3 class="panel-title" style="color:red">Red</h3>
                                                </div>
                                                <div class="panel-body">
                                                        <form action="index.php" method="GET">
                                                                <input type="submit" value="Choose Red"/>
                                                        </form>
                                                </div>
                                        </div>
                                </div>
                                <div class="col-md-6">
                                        <div class="panel panel-primary" style="margin-top:50px">
                                                <div class="panel-heading">
                                                        <h3 class="panel-title" style="color:blue">Blue</h3>
                                                </div>
                                                <div class="panel-body">
                                                        <form action="index.php" method="POST">
                                                                <input type="submit" value="Choose Blue"/>
                                                        </form>
                                                </div>
                                        </div>
                                </div>
                        </div>
                </div>
        </body>
</html>
```

Al parecer la página nos permite mandar otro tipo de solicitudes, si le mandamos un `HEAD` obtenemos lo siguiente: 
```
200 OK
Content-Type: text/html; charset=UTF-8
Client-Date: Wed, 26 Mar 2025 18:12:11 GMT
Client-Peer: 18.189.209.142:53554
Client-Response-Num: 1
Flag: picoCTF{r3j3ct_th3_du4l1ty_2e5ba39f}
```
En el encabezado de la página podemos obtener la bandera.