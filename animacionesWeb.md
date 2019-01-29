# Animaciones para la Web
#
# Índice
#

## [Introducción](#sec1)
### [Bienvenido al curso](#clase1)
### [Introducción a las animaciones y micro interacciones en la web](#clase2)

#

## [Transiciones](#sec2)
### [Sintaxis de transiciones](#clase3)
### [Transiciones de interacción](#clase4)

#

## [Transformaciones CSS](#sec3)
### [Sintaxis de Transformaciones](#clase5)
### [Transformaciones de rotación](#clase6)
### [Transformaciones de traslación y perspectiva](#clase7)
### [Transformaciones de escala](#clase8)
### [Transformaciones de sesgados](#clase9)
### [Punto de transformación](#clase10)

#

## [Animaciones CSS](#sec4)
### [Sintaxis](#clase11)
### [Aceleración y curva de bezier](#clase12)
### [Múltiples animaciones](#clase13)
### [Detectar eventos de animaciones CSS desde JS](#clase14)
### [Optimizar render con will-change y developer tools](#clase15)
### [Propiedades animables](#clase16)

#

## [Web Animations API (Animaciones en JS)](#sec5)
### [element.animate](#clase17)
### [Controlar animaciones](#clase18)
### [Estas listo para certificarte](#clase19)

#

## [Práctica: Tipos de animaciones en la web](#sec6)
### [Creando logo de platzi](#clase20)
### [Animando logo de platzi](#clase21)
### [Animaciones de Entrada y Salida](#clase22)
### [Creando un Modal](#clase23)
### [Animando el like de Twitter con Sprites](#clase24)
### [Creando un sistema de notificación](#clase25)
### [Animando Notificaciones](#clase26)
### [Olas Explicación](#clase27)
### [Olas Animación 2](#clase28)

#

## [Contenido bonus: Animaciones en ReactJS](#sec7)
### [Intro al proyecto final del curso](#clase29)
### [Configurando una aplicación en React JS](#clase30)
### [Estructura de proyectos con React](#clase31)
### [Animaciones con React Transicion Group](#clase32)
### [Llevando HTML y CSS a React JS](#clase33)
### [Pasando de una página estática a una dinámica con propiedades](#clase34)
### [Puliendo el CSS de invie](#clase35)
### [Añadiendo Cheet JS](#clase36)
### [Configurando Redux](#clase37)
### [Animando las guitarras](#clase38)
### [Transición en los Cards de Guitarras](#clase39)
### [Animación de entrada y salida en la portada](#clase40)
### [Animando el background de la portada](#clase41)
### [Multiplicando y animando los corazones](#clase42)
### [Cierre del Curso](#clase43)

<br>
<br>
<br>

# <a name="sec1">Introducción</a>

<br>
<br>

## <a name="clase1">Bienvenido al curso</a>



<br>
<br>
<br>

## <a name="clase2">Introducción a las animaciones y micro interacciones en la web</a>


Las animaciones son simplemente generar sensación de movimiento de algo.
Es la transición de un punto 'a' a un punto 'b'.

Las animaciones son parte natural de las interfaces. Es lo que ocurre cada vez que un usuario interactúa con esa interfaz y la interfaz le da un feed-back de que algo está ocurriendo.

Lo que aquí sucede es que el usuario envía una orden a la interfaz, esta la recibe - interpreta - y luego entrega el resultado, feedback o respuesta.

Las acciones que toman tiempo en ser procesadas son un evento natural o ideal para agregar animaciones.

La especificación de CSS 3 nos trae:

  + Transitions
  + Transform 
  + Animations

<br>
<br>
<br>

# <a name="sec2">Transiciones</a>

<br>
<br>

## <a name="clase3">Sintaxis de transiciones</a>

### Transitions

_**transition**_ es una propiedad de CSS3 para crear animaciones. 

> ...a partir de un evento en el navegador es posible hacer que las propiedades CSS de un elemento en el DOM cambien de forma continua. Por ejemplo un elemento de tamaño 'x' a tamaño 'y' en una determinada cantidad de tiempo, o de un color a otro, etc.


  + ```transition-duration: Xs | Xms;``` /* duración de la transición */

  + ```transition-property: none|all|property|initial|inherit;``` /* propiedades que afecta - opcional */
  + ```transition-delay: Xs | Xms;``` /* tiempo hasta disparar transición, en segundos o milisegundos - opcional */
  + ```transition-timing-function: ease | linear | ease-in | ease-out | ease-in-out | cubic-bezier(n,n,n,n)``` /* opcional */
  
  + ```transition: porperty | duration | delay | timing-function ;```   /* shorthand */
  
  
   + ```transition: porperty | duration | delay | timing-function ;```   /* shorthand */
  

_**transition-duration**_ es la única propiedad requerida para que funcione el efecto de transición. Si sólo uso esta propiedad, las _propiedades que cambian son todas_, el _delay es 0ms_ y el _timing-function_ es _ease_.

Ej: 

```html

<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <meta http-equiv="X-UA-Compatible" content="ie=edge">
    <title>Transition</title>
    <style>
        .ball {
            width: 200px;
            height: 200px;
            background-color: yellow;
            border-radius: 50%;
            transition-duration: 3s;
            /* transition-property: width, height */
            /* transition-delay: 0;    */
            /* transition-timing-function: ease; */

            /* Short Hand */
            /* transition: all 3s; */
        }
        .ball:hover{
            width: 300px;
            height: 300px;
            background-color: red;
        }
    </style>
</head>
<body>
    <div class="ball"> </div>
</body>
</html>


```

<br>
<br>
<br>

## <a name="clase4">Transiciones de interacción</a>

Para aplicar transiciones a múltiples elementos utilizo un elemento padre.

```html

  <style>
    .pelota {
      background-color: rojo;
    }
    .canasta {
      transition-duration: 1.5s;
    }
    .canasta:hover .pelota{
      background-color: azul;     
    }
  </style>
  <div class="canasta">
    <div class="pelota a">
    <div class="pelota b">
  </div>

```

Ej:


```html

<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <meta http-equiv="X-UA-Compatible" content="ie=edge">
    <title>Transition</title>
    <style>
        body {
            display: flex;
            height: 100vh;
            justify-content: center;
            align-items: center;
            background-color: black;
        }
        .container{
            height: 100px;
            width: 100vw;
            border: 1px solid black;
            transition-duration: 1.5s;
        }
        .ball {
            position: absolute;
            display: flex;
            width: 100px;
            height: 100px;
            background-color: yellow;
            border-radius: 50%;
            transition-duration: 1.5s;
            align-items: center;
            justify-content: center;
            font-family: Verdana, Geneva, Tahoma, sans-serif;
        }
        .ball p {
            opacity: 0;
            font-size: 15px;
            transition-duration: 1.5s;
        }
        .ball.a {
            left: 0;
        }
        .ball.b{
            right: 0;
        }
        .container:hover .ball {
            background-color: red;
            width: 300px;
            height: 300px;
        }
        .container:hover .ball.a{
            left: calc(50vw - 150px);
        }
        .container:hover .ball.b{
            right: calc(50vw - 150px);
        }
        .container:hover .ball p {
            font-size: 30px;
            opacity: 1;
        }
        .container:hover {
            height: 300px;
        }
    </style>
</head>
<body>
    <div class="container">
        <div class="ball a"><p>Hate</p></div>
        <div class="ball b"><p>Love</p></div>
    </div>
</body>
</html>



```


<br>
<br>
<br>

# <a name="sec3">Transformaciones CSS</a>

<br>
<br>

## <a name="clase5">Sintaxis de Transformaciones</a>

[_Transform_](https://www.w3schools.com/cssref/css3_pr_transform.asp) es una propiedad muy utilizada en CSS3.
Esta nos permite manipular un elemento de las siguientes maneras:

  + ```mover```
  + ```escalar```
  + ```sesgar```
  + ```rotar```
  
  Sintaxis:
  
    transform: none|transform-functions|initial|inherit;

  Sintaxis JavaScript
 
    object.style.transform="rotate(7deg)"

  Propiedades:
  
   + translate()
   + scale()
   + rotate()
   + skew()

Ejemplo de sintaxis:

```html

  <style>
    .canasta {
      transform: translate(50px) scale(1.5) rotate(15deg) skew(30deg);
    }
  </style>
  <div class="canasta">
    <div class="pelota a">
    <div class="pelota b">
  </div>


```


<br>
<br>
<br>

## <a name="clase6">Transformaciones de rotación</a>

La propiedad _ transform: rotate(angle)_ nos permite hacer la rotación de un objeto.

Hay 3 ejes posibles para hacer rotaciones:

  + X - rotateX() - rotación horizontal   :arrow_up_down:
  + Y - rotateY() - rotación vertical     :left_right_arrow:
  + Z _ rotateZ() - rotación eje central  :arrows_counterclockwise:

Por defecto _rotate()_ refiere a la rotación del eje Z, por lo tanto:

    rotate(Xdeg) == rotateZ(Xdeg)

Un valor positivo rotará en sentido de las agujas del relog y un valor negativo en sentido reverso:

   ```rotate(45deg)``` :leftwards_arrow_with_hook:
  
   ```rotate(-45deg)``` :arrow_right_hook:
  

También puedo rotar el elemento en 2 o 3 ejes a la vez:

  ```transform: rotateX(Xdeg) rotateY(Xdeg) rotateZ(Xdeg);```

  ```transform: rotate3d(0, 1, 0, -45deg);```


Cuando aplico _transition_, una buena práctica es referirse siempre al padre del elemento, ya que si por ejemplo hago un hover en la esquina del mismo, cuando este empieza a rotar mi hover ya no está sobre el elemento porque este se "corrió" y esto generalmente provoca un fallo en el funcionamiento.

```html

    <style>
        .cuadrado {
            transition-duration: Xs;
        }
        .container:hover .cuadrado {
            transform: rotate(Xdeg);
        }
    </style>
    <div class="container">
      <div class="cuadrado">
      </div>
    </div>

```

Ej: 

```html

<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <meta http-equiv="X-UA-Compatible" content="ie=edge">
    <title>Transformation rotate</title>
    <style>
        body{
            display: flex;
            align-items: center;
            justify-content: center;
            height: 100vh;
            color: white;
            font-family: Arial, Helvetica, sans-serif;
        }
        .container {
            border: 2px solid red;
        }
        .cuadrado {
            width: 200px;
            height: 200px;
            display: inline-block;
            background-color: #7dc900;
            margin: 20px;
            box-shadow: 0 0 50px #000;
            transition-duration: 2s;
        }
        .container:hover .cuadrado.a {
            transform: rotate(45deg);
        }
        .container:hover .cuadrado.b {
            transform: rotateX(45deg);
        }
        .container:hover .cuadrado.c {
            transform: rotateY(45deg);
        }
        .container:hover .cuadrado.d {
            transform: rotateX(30deg) rotateY(15deg) rotateZ(90deg);
        }
        .container:hover .cuadrado.e {
            transform: rotate3d(0, 1, 0, -45deg);
        }
        .container:hover .cuadrado.f {
            transform: rotate(-45deg);
        }
    </style>
</head>
<body>
    <div class="container">
        <div class="cuadrado a">
        </div>
        <div class="cuadrado b">
        </div>
        <div class="cuadrado c">
        </div>
        <div class="cuadrado d">
        </div>
        <div class="cuadrado e">
        </div>
        <div class="cuadrado f">
        </div>
    </div>
</body>
</html>


```

![image](https://developerathome.tk/Store/images/CSSrotate.gif)

<img src="https://developerathome.tk/Store/images/CSSrotate.gif" style="float: center; margin-right: 10px;" />

[Ejemplo fancy...](https://codepen.io/thebabydino/pen/MeeqLB)

![image](https://developerathome.tk/Store/images/CSS3Drotate.gif)

<br>
<br>
<br>

## <a name="clase7">Transformaciones de translación y perspectiva</a>

La propiedad _transform: translate()_ nos permite hacer la translación de un objeto.

Hablando de animaciones en 2D, puedo mover los objetos sobre el eje X o sobre el eje Y:

    translate(x,y)
    translateX(n)
    translateY(n)


También es posible generar movimiento en 3D utilizando la propiedad _perspective_ en el body (en firefox agregar _transform-style: preserve-3d;_ al padre del objeto a mover) y la propiedad _transform: translateZ()_ en el objeto.

Al agregar la propiedad _perspective-origin_ al padre, body en este caso, puedo mover el foco de la perspectiva a cualquier lugar de la ventana. Por defecto el punto de foco de la perspectiva es el centro.
La propiedad que nos lo permite:

    perspective-origin: x y | px | % | ... | top | left | bottom | right

Ej:

```html

  <style>
    body{
      display: flex;
      align-items: center;
      justify-content: center;
      height: 100vh;
      perspective: 500px;
      perspective-origin: 10vw 10vh;
    }
    .container:hover .box {
      transform: translateZ(50px);
    }
  </style>
  <body>
     <div class="container">
       <div class="box"></div>
    </div>
  </body>


```

La propiedad _translate3d()_ nos permite manipular todos los ejes a la vez: 

    translate3d(x, y, z)

```html

    .container:hover .box {
      transform: translate3d(20px, -50px, 35px);
    }

```

<br>
<br>
<br>

## <a name="clase8">Transformaciones de escala</a>


```transform: scale()``` modifica el tamaño de cualquier objeto dentro del DOM.

```scale()``` recibe x e y como parámetros en decimales, es decir entre 0 y 1 correspondiendo con el porcentaje de tamaño.

    0 == 0%
    0.5 == 50%
    1 == 100%
 
 Ej:
 
    transform: scale(.7, 1.3)
    
 Si en vez de cargar los datos _x_ e _y_ cargo sólo un dato, el objeto se modificará en igual proporción tanto en el eje _x_ como en el _y_

 Ej:

    transform: scale(.5)



<br>
<br>
<br>

## <a name="clase9">Transformaciones de sesgado</a>


Con ```transform: skew(Xdeg)``` podemos manipular el sesgado del elemento.
```transform: skew()``` recibe dos parámetros en grados, parámetro 'x' y parámetro 'y', cada uno modifica el eje que representa. Si sólo inserto 1 valor el eje modificado será el eje 'x'.

Al igual que los otros métodos de _transform_ skew tiene sus variables para cada eje:

      skewX()
      skewY()


```css

  transform: skew(25deg);

  transform: skew(25deg, 10deg);

  transform: skewX(24deg);
  transform: skewY(45deg);


```


<br>
<br>
<br>

## <a name="clase10">Punto de transformación</a>

Por defecto, el punto de transformación de los objetos en la propiedad de CSS _transform_ está en el centro. 
Podemos modificar la ubicación del punto con la propiedad [_transform-origin_](https://developer.mozilla.org/en-US/docs/Web/CSS/transform-origin).

    transform-origin: x% y% z%; /*   % || <length>  values  */

    transform-origin: center top right; /* sugar syntax */

Por defecto, si inserto sólo un valor se modificará solamente el eje 'x' y los otros dos segiran centrados, si inserto 2 valores, 'x' e 'y' y 'z' será 'center'.

Ej:

```html

      <style>
          body{
              display: flex;
              align-items: center;
              justify-content: center;
              height: 100vh;
          }
          .container {
              border: 2px solid red;
          }
          .cuadrado {
              width: 200px;
              height: 200px;
              display: inline-block;
              background-color: #7dc900;
              margin: 20px;
              box-shadow: 0 0 50px #000;
              transition-duration: 1s;
          }
          .container:hover .cuadrado {
              transform-origin: 60px bottom;
              transform: rotateZ(90deg);
          }
      </style>

      <body>
          <div class="container">
              <div class="cuadrado a">
              </div>
          </div>
      </body>

```



<br>
<br>
<br>

# <a name="sec4">Animaciones CSS</a>

<br>
<br>

## <a name="clase11">Sintaxis</a>

<br>
<br>
<br>

## <a name="clase12">Aceleración y curva de bezier</a>

<br>
<br>
<br>

## <a name="clase13">Múltiples animaciones</a>

<br>
<br>
<br>

## <a name="clase14">Detectar eventos de animaciones</a>

<br>
<br>
<br>

## <a name="clase15">Optimizar render con will-change y developer tools</a>


<br>
<br>
<br>

## <a name="clase16">Propiedades Animables</a>


<br>
<br>
<br>

# <a name="sec5">Web Animations API (Animaciones en JS)</a>

<br>
<br>

## <a name="clase11">element.animate</a>

<br>
<br>
<br>

## <a name="clase12">Controlar Animaciones</a>

<br>
<br>
<br>

## <a name="clase13">Estás listo para certificarte</a>

