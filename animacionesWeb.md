# Animaciones para la Web
#
# <a name="index">Índice</a>
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

[Volver al índice](#index)

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

[Volver al índice](#index)

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

[Volver al índice](#index)

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

[Volver al índice](#index)


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

[Volver al índice](#index)

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

[Volver al índice](#index)

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

[Volver al índice](#index)


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

[Volver al índice](#index)

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

[Volver al índice](#index)


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

[Volver al índice](#index)

<br>
<br>
<br>

# <a name="sec4">Animaciones CSS</a>

<br>
<br>

## <a name="clase11">Sintaxis</a>

Con la propiedad [```animation```](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Animations/Using_CSS_animations) puedo hacer animaciones de cualquier propiedad visual de CSS en una cantidad determinada de tiempo.
Para que funcione, la sintaxis básica es ```animation-name``` y ```animation-duration``` en el elemento que deseamos animar. Y un ```@keyframes``` apuntando al nombre previamente seteado.

```css

  .objeto {
    animation-name: objeto1;
    animation-time: 2s;
  }
  @keyframes objeto1 {
    from {background-color: red;}
    to {background-color: yellow;}
  }


```
El ```@keyframes``` puede usarse con los keywords "from" y "to" ó con porcentajes cuándo necesito más de un cambio durante el tiempo seteado.

```css

  @keyframes objeto1 {
    0% { background-color: red; }
    25% { background-color: orange; }
    50% { background-color: dark-orange; }
    100% { background-color: yellow; }
  }


```

Al terminar el ```animation``` el objeto vuelve a su estado original salvo lo configuremos para que la animación se convierta en un loop.

Otras propiedades:

  + ```animation-delay: Xs```  - tiempo después de la carga de la página hasta que comienza el efecto. [Referencia](https://developer.mozilla.org/en-US/docs/Web/CSS/animation-delay)
  + ```animation-iteration-count: n | infinite``` - cantidad de veces que se repetirá el efecto. [Referencia](https://developer.mozilla.org/en-US/docs/Web/CSS/animation-iteration-count)
  + ```animation-timing-function: ease | cubic-bezier() | steps()``` - cómo es el progreso de la animación a traves del tiempo. [Referencia](https://developer.mozilla.org/en-US/docs/Web/CSS/animation-timing-function)
  + ```animation-direction: normal | reverse | alternate``` determina la dirección de la animación y si se repite y de qué manera. [Referencia](https://developer.mozilla.org/en-US/docs/Web/CSS/animation-direction)
  + ```animation-fill-mode: forwards | backwards | both``` setear estilos antes y después de la animación. [Referencia](https://developer.mozilla.org/en-US/docs/Web/CSS/animation-fill-mode)
  + ```animation-play-state: running | paused``` detiene la animación en el momento en el que está. [Referencia](https://developer.mozilla.org/en-US/docs/Web/CSS/animation-play-state)
  


<br>

[Volver al índice](#index)

<br>
<br>
<br>

## <a name="clase12">Aceleración y curva de bezier</a>

Para hacer animaciones debemos tener en cuenta el factor de la aceleración.
El parámetro que nos permite hacer esto es [```animation-timing-function```](https://developer.mozilla.org/en-US/docs/Web/CSS/animation-timing-function).

```animation-timing-function``` presenta varias opciones para modificar el tipo de aceleración que podemos darle a nuesto objeto.


```
    /* valores predefinidos - keywords */
    animation-timing-function: ease;
    animation-timing-function: ease-in;
    animation-timing-function: ease-out;
    animation-timing-function: ease-in-out;
    animation-timing-function: linear;
    animation-timing-function: step-start;
    animation-timing-function: step-end;

    /* Funciones */
    animation-timing-function: cubic-bezier(0.1, 0.7, 1.0, 0.1);
    animation-timing-function: steps(4, end);

    /* Keywords para function step() */ 
    animation-timing-function: steps(4, jump-start);
    animation-timing-function: steps(10, jump-end);
    animation-timing-function: steps(20, jump-none);
    animation-timing-function: steps(5, jump-both);
    animation-timing-function: steps(6, start);
    animation-timing-function: steps(8, end);

    /* Animaciones Múltiples */
    animation-timing-function: ease, step-start, cubic-bezier(0.1, 0.7, 1.0, 0.1);

    /* Valores Globales */
    animation-timing-function: inherit;
    animation-timing-function: initial;
    animation-timing-function: unset;

```

  Los keywords como ease o esae-in-out lo que hacen es mover el objeto de acuerdo a una velocidad preseteada. 
  Las funciones nos permiten personalizar el tipo de aceleración más allá de las posibilidades de los keywords.

  La función [```cubic-bezier()```](https://developer.mozilla.org/en-US/docs/Web/CSS/timing-function) nos permite generar nuestra propia curva de movimiento a partir de 4 parámetros entre 0 y 1 positivo o negativos para generar 'rebotes'.
  
      cubic-bezier(x1, y1, x2, y2)

  Una herramienta gráfica para modificar los valores de la curva [aquí](http://cubic-bezier.com).


  La función [```steps()```](https://developer.mozilla.org/en-US/docs/Web/CSS/timing-function) funciona con 2 parámetros, un número entero para la cantidad de 'pasos' y un keyword que indica si la función es continua hacia izquierda o derecha.
  
      steps( n, <direction> )
      
  Si uso sólo el valor numérico, este representará la cantidad de cuadros en el tiempo que dure mi animación. Entonces, por ejemplo podemos decir que un ```steps(60)``` con un ```animation-duration: 2s``` dará como resultado una animación de 30 cuadros por segundo.
  El segundo parámetro (keyword) es un valor para configurar el estado entre 'steps' o cuadros.

  + start - comienza moviéndose y se queda en el lugar hasta el estado siguiente
  + end - se queda en su lugar hasta el siguiente step en el que se mueve y repite el movimiento.
  + none
  + both
  
  


<br>

[Volver al índice](#index)

<br>
<br>
<br>

## <a name="clase13">Múltiples animaciones</a>

Para generar una múltiple animación a un mismo objeto tengo que configurar otro ```@keyframes```.
Para esto, tengo primero que generar otro ```animation-name```, lo que hago agregando una ',' al ```action-name``` ya declarado:

    animation-name: cuadrado, otraAnimacion;

Esto nos permite generar otro ```@keyframes``` con una nueva animación.

    @keyframes otraAnimacion { }

Todas las propiedades de animación ya declaradas se pasan automáticamente a este segundo ```@keyframes```. Si quiero propiedades diferentes las agrego luego de una ',' a las propiedades ya declaradas.

Ej: 

      animation-timing-function: linear, ease-out;
      animation-duration: 3s, 300ms;


Ejemplo completo:


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
              width: 100vw;
              /* transform: rotate(270deg) */
          }
          .cuadrado {
              width: 200px;
              height: 200px;
              border-radius: 50%;
              display: inline-block;
              position: relative;
              background-color: #7dc900;
              animation-name: cuadrado, secAnimation;
              animation-duration: 3s, 300ms;
              animation-iteration-count: infinite;
              animation-direction: alternate;
              animation-timing-function: linear, ease-out;
          }
          @keyframes cuadrado{
              0% {
                  left: 0;
              }
              100% {
                  left: calc(100% - 200px);
              }
          }
          @keyframes secAnimation {
              from {
                  bottom: 0;
                  transform: scale(1,.9);
              }
              to {
                  bottom: 30vh;
                  transform: scale(1,1);
              }
          }

      </style>
  </head>
  <body>
      <div class="container">
          <div class="cuadrado a">
          </div>
      </div>
  </body>
  </html>


```


<br>

[Volver al índice](#index)

<br>
<br>
<br>

## <a name="clase14">Detectar eventos de animaciones</a>

Para detectar un evento en las animaciones puedo usar javascript.

En principio localizo el objeto con ```document.getElementById()``` pasando como parámetro el id del objeto sobre el que se ejecuta la animación.

      const $objeto = document.getElementById('objeto')

Cargo luego un oyente de eventos ```addEventListener()``` para detectar el fin de la animación con ```animationend```.
Y finalmente gatillo la animación extra a travez de la función del listener.

      $objeto.addEventListener('animationend', function(){
        /* disparo la siguiente animación aquí */
      })

Para gatillar la función siguiente utilizo la propiedad [```.style.animation```](https://www.w3schools.com/jsref/prop_style_animation.asp) de javascript. Los básicos para que funcione son ```animationName``` y ```animationDuration```.

      $objeto.style.animationName = 'animacionDeObjeto'
      $objeto.style.animationDuration = 'Xs'


Otras propiedades:

  + [animationName](https://www.w3schools.com/jsref/prop_style_animationname.asp)
  + [animationDuration](https://www.w3schools.com/jsref/prop_style_animationduration.asp)
  + [animationTimingFunction](https://www.w3schools.com/jsref/prop_style_animationtimingfunction.asp)
  + [animationDelay](https://www.w3schools.com/jsref/prop_style_animationdelay.asp)
  + [animationIterationCount](https://www.w3schools.com/jsref/prop_style_animationiterationcount.asp)
  + [animationDirection](https://www.w3schools.com/jsref/prop_style_animationdirection.asp)
  + [animationFillMode](https://www.w3schools.com/jsref/prop_style_animationfillmode.asp)
  + [animationPlayState](https://www.w3schools.com/jsref/prop_style_animationplaystate.asp)

Otros listeners:

  + [```animationstart```](https://www.w3schools.com/jsref/event_animationstart.asp)
  + [```animationiteration```](https://www.w3schools.com/jsref/event_animationiteration.asp)
  + [```animationend```](https://www.w3schools.com/jsref/event_animationend.asp)



<br>

[Volver al índice](#index)

<br>
<br>
<br>

## <a name="clase15">Optimizar render con will-change y developer tools</a>

Con los developer tools de Chrome podemos verificar varias cosas en las animaciones con CSS3; podemos incluso probar cambios y optimizar el rendering.

Para usarlo abro el inspector y en los 3 puntos verticales de la esquina superior derecha de la ventana del mismo puedo ir a la pestaña 'More Tools' > 'Animations' o 'More Tools' > 'Render'. Esto agregará una pestaña nueva para cada herramienta en la misma ventana del 'console'.


<p align="center">
  <img src="https://developerathome.tk/Store/images/devTools1.gif" alt="dev tools gif 1" width="300"/>
  
  <img src="https://developerathome.tk/Store/images/devTools2.gif" alt="dev tools gif 1" width="300"/>
</p>

Otra herramienta que puede ser útil desde CSS3 es ```will-change```.
```will-change``` prepara (avisa/notifica) al navegador para que al renderizar una animación no genere impresiones extra del objeto o imagen que 'va a cambiar'.

[developer.mozilla.org](https://developer.mozilla.org/es/docs/Web/CSS/will-change) nos advierte que ```will-change``` es para ser usado sólo como un último recurso en situaciones de problemas existentes de performance y no para 'anticipar' problemas.

Dicho esto los recursos para los que ```will-change```está optimizado son ```opacity``` y ```transform``` aunque mozilla agrega [otros](https://developer.mozilla.org/es/docs/Web/CSS/will-change).

Sintaxis ejemplo:

```css

    .cuadrado {
        width: 200px;
        height: 200px;
        background-color: #000;
        transition-duration: 2s;
        opacity: 1;
        will-change: opacity, transform;
    }
    .container:hover .cuadrado {
        opacity: 0;
        transform: scale(1.5, 0.5);
    }


```


[Volver al índice](#index)

<br>
<br>

## <a name="clase16">Propiedades Animables</a>


Las propiedades que son posibles de animar en HTML y CSS son las siguientes:




  <ul>
     <li><a href="https://developer.mozilla.org/en-US/docs/Web/CSS/-moz-outline-radius" target="_blank" title="In Mozilla applications like Firefox, the -moz-outline-radius CSS property can be used to give an element's outline rounded corners."><code>-moz-outline-radius</code></a></li>
     <li><a href="https://developer.mozilla.org/en-US/docs/Web/CSS/-moz-outline-radius-bottomleft" target="_blank" title="In Mozilla applications, the -moz-outline-radius-bottomleft CSS property can be used to round the bottom-left corner of an element's outline."><code>-moz-outline-radius-bottomleft</code></a></li>
     <li><a href="https://developer.mozilla.org/en-US/docs/Web/CSS/-moz-outline-radius-bottomright" target="_blank" title="In Mozilla applications, the -moz-outline-radius-bottomright CSS property can be used to round the bottom-right corner of an element's outline."><code>-moz-outline-radius-bottomright</code></a></li>
     <li><a href="https://developer.mozilla.org/en-US/docs/Web/CSS/-moz-outline-radius-topleft" target="_blank" title="In Mozilla applications, the -moz-outline-radius-topleft CSS property can be used to round the top-left corner of an element's outline."><code>-moz-outline-radius-topleft</code></a></li>
     <li><a href="https://developer.mozilla.org/en-US/docs/Web/CSS/-moz-outline-radius-topright" target="_blank" title="In Mozilla applications, the -moz-outline-radius-topright CSS property can be used to round the top-right corner of an element's outline."><code>-moz-outline-radius-topright</code></a></li>
     <li><a href="https://developer.mozilla.org/en-US/docs/Web/CSS/-webkit-text-fill-color" target="_blank" title="The -webkit-text-fill-color CSS property specifies the fill color of characters of text. If this property is not set, the value of the color property is used."><code>-webkit-text-fill-color</code></a></li>
     <li><a href="https://developer.mozilla.org/en-US/docs/Web/CSS/-webkit-text-stroke" target="_blank" title="The -webkit-text-stroke CSS property specifies the width and color of strokes for text characters. This is a shorthand property for the longhand properties -webkit-text-stroke-width and -webkit-text-stroke-color."><code>-webkit-text-stroke</code></a></li>
     <li><a href="https://developer.mozilla.org/en-US/docs/Web/CSS/-webkit-text-stroke-color" target="_blank" title="The -webkit-text-stroke-color CSS property specifies the stroke color of characters of text. If this property is not set, the value of the color property is used."><code>-webkit-text-stroke-color</code></a></li>
     <li><a href="https://developer.mozilla.org/en-US/docs/Web/CSS/all" target="_blank" title="The all CSS shorthand property sets all of an element's properties (other than unicode-bidi and direction) to their initial or inherited values, or to the values specified in another stylesheet origin."><code>all</code></a></li>
     <li><a href="https://developer.mozilla.org/en-US/docs/Web/CSS/backdrop-filter" target="_blank" title="The backdrop-filter CSS property lets you apply graphical effects such as blurring or color shifting to the area behind an element. Because it applies to everything behind the element, to see the effect you must make the element or its background at least partially transparent."><code>backdrop-filter</code></a></li>
     <li><a href="https://developer.mozilla.org/en-US/docs/Web/CSS/background" target="_blank" title="The background shorthand CSS property sets all background style properties at once, such as color, image, origin and size, or repeat method."><code>background</code></a></li>
     <li><a href="https://developer.mozilla.org/en-US/docs/Web/CSS/background-color" target="_blank" title="The background-color CSS property sets the background color of an element."><code>background-color</code></a></li>
     <li><a href="https://developer.mozilla.org/en-US/docs/Web/CSS/background-position" target="_blank" title="The background-position CSS property sets the initial position for each background image. The position is relative to the position layer set by background-origin."><code>background-position</code></a></li>
     <li><a href="https://developer.mozilla.org/en-US/docs/Web/CSS/background-size" target="_blank" title="The background-size CSS property sets the size of the element's background image. The image can be left to its natural size, stretched, or constrained to fit the available space."><code>background-size</code></a></li>
     <li><a href="https://developer.mozilla.org/en-US/docs/Web/CSS/border" target="_blank" title="The border CSS property sets an element's border. It's a shorthand for border-width, border-style, and border-color."><code>border</code></a></li>
     <li><a href="https://developer.mozilla.org/en-US/docs/Web/CSS/border-bottom" target="_blank" title="The border-bottom CSS property is a shorthand that sets the values of border-bottom-width, border-bottom-style and border-bottom-color."><code>border-bottom</code></a></li>
     <li><a href="https://developer.mozilla.org/en-US/docs/Web/CSS/border-bottom-color" target="_blank" title="The border-bottom-color CSS property sets the color of an element's bottom border. It can also be set with the shorthand CSS properties border-color or border-bottom."><code>border-bottom-color</code></a></li>
     <li><a href="https://developer.mozilla.org/en-US/docs/Web/CSS/border-bottom-left-radius" target="_blank" title="The border-bottom-left-radius CSS property rounds the bottom-left corner of an element."><code>border-bottom-left-radius</code></a></li>
     <li><a href="https://developer.mozilla.org/en-US/docs/Web/CSS/border-bottom-right-radius" target="_blank" title="The border-bottom-right-radius CSS property rounds the bottom-right corner of an element."><code>border-bottom-right-radius</code></a></li>
     <li><a href="https://developer.mozilla.org/en-US/docs/Web/CSS/border-bottom-width" target="_blank" title="The border-bottom-width CSS property sets the width of the bottom border of a box."><code>border-bottom-width</code></a></li>
     <li><a href="https://developer.mozilla.org/en-US/docs/Web/CSS/border-color" target="_blank" title="The border-color shorthand CSS property sets the color of all sides of an element's border."><code>border-color</code></a></li>
     <li><a href="https://developer.mozilla.org/en-US/docs/Web/CSS/border-end-end-radius" target="_blank" title="The border-end-end-radius CSS property defines a logical border radius on an element, which maps to a physical border radius that depends on on the element's writing-mode, direction, and text-orientation."><code>border-end-end-radius</code></a></li>
     <li><a href="https://developer.mozilla.org/en-US/docs/Web/CSS/border-end-start-radius" target="_blank" title="The border-end-start-radius CSS property defines a logical border radius on an element, which maps to a physical border radius depending on the element's writing-mode, direction, and text-orientation."><code>border-end-start-radius</code></a></li>
     <li><a href="https://developer.mozilla.org/en-US/docs/Web/CSS/border-left" target="_blank" title="The border-left CSS property is a shorthand that sets the values of border-left-width, border-left-style and border-left-color."><code>border-left</code></a></li>
     <li><a href="https://developer.mozilla.org/en-US/docs/Web/CSS/border-left-color" target="_blank" title="The border-left-color CSS property sets the color of an element's left border. It can also be set with the shorthand CSS properties border-color or border-left."><code>border-left-color</code></a></li>
     <li><a href="https://developer.mozilla.org/en-US/docs/Web/CSS/border-left-width" target="_blank" title="The border-left-width CSS property sets the width of the left border of an element."><code>border-left-width</code></a></li>
     <li><a href="https://developer.mozilla.org/en-US/docs/Web/CSS/border-radius" target="_blank" title="The border-radius CSS property rounds the corners of an element's outer border edge. You can set a single radius to make circular corners, or two radii to make elliptical corners."><code>border-radius</code></a></li>
     <li><a href="https://developer.mozilla.org/en-US/docs/Web/CSS/border-right" target="_blank" title="The border-right CSS property is a shorthand that sets the values of border-right-width, border-right-style and border-right-color."><code>border-right</code></a></li>
     <li><a href="https://developer.mozilla.org/en-US/docs/Web/CSS/border-right-color" target="_blank" title="The border-right-color CSS property sets the color of an element's right border. It can also be set with the shorthand CSS properties border-color or border-right."><code>border-right-color</code></a></li>
     <li><a href="https://developer.mozilla.org/en-US/docs/Web/CSS/border-right-width" target="_blank" title="The border-right-width CSS property sets the width of the right border of an element."><code>border-right-width</code></a></li>
     <li><a href="https://developer.mozilla.org/en-US/docs/Web/CSS/border-start-end-radius" target="_blank" title="The border-start-end-radius CSS property defines a logical border radius on an element, which maps to a physical border radius depending on the element's writing-mode, direction, and text-orientation."><code>border-start-end-radius</code></a></li>
     <li><a href="https://developer.mozilla.org/en-US/docs/Web/CSS/border-start-start-radius" target="_blank" title="The border-start-start-radius CSS property defines a logical border radius on an element, which maps to a physical border radius that depends on the element's writing-mode, direction, and text-orientation."><code>border-start-start-radius</code></a></li>
     <li><a href="https://developer.mozilla.org/en-US/docs/Web/CSS/border-top" target="_blank" title="The border-top CSS property is a shorthand that sets the values of border-top-width, border-top-style and border-top-color."><code>border-top</code></a></li>
     <li><a href="https://developer.mozilla.org/en-US/docs/Web/CSS/border-top-color" target="_blank" title="The border-top-color CSS property sets the color of an element's top border. It can also be set with the shorthand CSS properties border-color or border-top."><code>border-top-color</code></a></li>
     <li><a href="https://developer.mozilla.org/en-US/docs/Web/CSS/border-top-left-radius" target="_blank" title="The border-top-left-radius CSS property rounds the top-left corner of an element."><code>border-top-left-radius</code></a></li>
     <li><a href="https://developer.mozilla.org/en-US/docs/Web/CSS/border-top-right-radius" target="_blank" title="The border-top-right-radius CSS property rounds the top-right corner of an element."><code>border-top-right-radius</code></a></li>
     <li><a href="https://developer.mozilla.org/en-US/docs/Web/CSS/border-top-width" target="_blank" title="The border-top-width CSS property sets the width of the top border of an element."><code>border-top-width</code></a></li>
     <li><a href="https://developer.mozilla.org/en-US/docs/Web/CSS/border-width" target="_blank" title="The border-width shorthand CSS property sets the widths of all four sides of an element's border."><code>border-width</code></a></li>
     <li><a href="https://developer.mozilla.org/en-US/docs/Web/CSS/bottom" target="_blank" title="The bottom CSS property participates in specifying the vertical position of a positioned element. It has no effect on non-positioned elements."><code>bottom</code></a></li>
     <li><a href="https://developer.mozilla.org/en-US/docs/Web/CSS/box-shadow" target="_blank" title="The box-shadow CSS property adds shadow effects around an element's frame. You can set multiple effects separated by commas."><code>box-shadow</code></a></li>
     <li><a href="https://developer.mozilla.org/en-US/docs/Web/CSS/caret-color" target="_blank" title="The caret-color CSS property sets the color of the insertion caret, the visible marker where the next character typed will be inserted."><code>caret-color</code></a></li>
     <li><a href="https://developer.mozilla.org/en-US/docs/Web/CSS/clip" target="_blank" title="The clip CSS property defines what portion of an element is visible. The clip property applies only to absolutely positioned elements, that is elements with position:absolute or position:fixed."><code>clip</code></a></li>
     <li><a href="https://developer.mozilla.org/en-US/docs/Web/CSS/clip-path" target="_blank" title="The clip-path CSS property creates a clipping region that sets what part of an element should be shown. Parts that are inside the region are shown, while those outside are hidden."><code>clip-path</code></a></li>
     <li><a href="https://developer.mozilla.org/en-US/docs/Web/CSS/color" target="_blank" title="The color CSS property sets the foreground color value of an element's text and text decorations, and sets the currentcolor value."><code>color</code></a></li>
     <li><a href="https://developer.mozilla.org/en-US/docs/Web/CSS/column-count" target="_blank" title="The column-count CSS property breaks an element's content into the specified number of columns."><code>column-count</code></a></li>
     <li><a href="https://developer.mozilla.org/en-US/docs/Web/CSS/column-gap" target="_blank" title="The column-gap CSS property sets the size of the gap (gutter) between an element's columns."><code>column-gap</code></a></li>
     <li><a href="https://developer.mozilla.org/en-US/docs/Web/CSS/column-rule" target="_blank" title="The column-rule CSS property sets the width, style, and color of the rule (line) drawn between columns in a multi-column layout."><code>column-rule</code></a></li>
     <li><a href="https://developer.mozilla.org/en-US/docs/Web/CSS/column-rule-color" target="_blank" title="The column-rule-color CSS property sets the color of the rule (line) drawn between columns in a multi-column layout."><code>column-rule-color</code></a></li>
     <li><a href="https://developer.mozilla.org/en-US/docs/Web/CSS/column-rule-width" target="_blank" title="The column-rule-width CSS property sets the width of the rule (line) drawn between columns in a multi-column layout."><code>column-rule-width</code></a></li>
     <li><a href="https://developer.mozilla.org/en-US/docs/Web/CSS/column-width" target="_blank" title="The column-width CSS property specifies the ideal column width in a multi-column layout."><code>column-width</code></a></li>
     <li><a href="https://developer.mozilla.org/en-US/docs/Web/CSS/columns" target="_blank" title="The columns CSS property sets the column width and column count of an element."><code>columns</code></a></li>
     <li><a href="https://developer.mozilla.org/en-US/docs/Web/CSS/filter" target="_blank" title="The filter CSS property applies graphical effects like blur or color shift to an element. Filters are commonly used to adjust the rendering of images, backgrounds, and borders."><code>filter</code></a></li>
     <li><a href="https://developer.mozilla.org/en-US/docs/Web/CSS/flex" target="_blank" title="The flex CSS property sets how a flex item will grow or shrink to fit the space available in its flex container. It is a shorthand for flex-grow, flex-shrink, and flex-basis."><code>flex</code></a></li>
     <li><a href="https://developer.mozilla.org/en-US/docs/Web/CSS/flex-basis" target="_blank" title="The flex-basis CSS property sets the initial main size of a flex item. It sets the size of the content box unless otherwise set with box-sizing."><code>flex-basis</code></a></li>
     <li><a href="https://developer.mozilla.org/en-US/docs/Web/CSS/flex-grow" target="_blank" title="The flex-grow CSS property sets how much of the available space in the flex container should be assigned to that item (the flex grow factor)."><code>flex-grow</code></a></li>
     <li><a href="https://developer.mozilla.org/en-US/docs/Web/CSS/flex-shrink" target="_blank" title="The flex-shrink CSS property sets the flex shrink factor of a flex item. If the size of flex items is larger than the flex container, items shrink to fit according to flex-shrink."><code>flex-shrink</code></a></li>
     <li><a href="https://developer.mozilla.org/en-US/docs/Web/CSS/font" target="_blank" title="The font CSS property is a shorthand for font-style, font-variant, font-weight, font-size, line-height, and font-family. Alternatively, it sets an element's font to a system font."><code>font</code></a></li>
     <li><a href="https://developer.mozilla.org/en-US/docs/Web/CSS/font-size" target="_blank" title="The font-size CSS property sets the size of the font."><code>font-size</code></a></li>
     <li><a href="https://developer.mozilla.org/en-US/docs/Web/CSS/font-size-adjust" target="_blank" title="The font-size-adjust CSS property sets how the font size should be chosen based on the height of lowercase rather than capital letters."><code>font-size-adjust</code></a></li>
     <li><a href="https://developer.mozilla.org/en-US/docs/Web/CSS/font-stretch" target="_blank" title="The font-stretch CSS property selects a normal, condensed, or expanded face from a font."><code>font-stretch</code></a></li>
     <li><a href="https://developer.mozilla.org/en-US/docs/Web/CSS/font-variation-settings" target="_blank" title="The font-variation-settings CSS property provides low-level control over variable font characteristics, by specifying the four letter axis names of the characteristics you want to vary, along with their values."><code>font-variation-settings</code></a></li>
     <li><a href="https://developer.mozilla.org/en-US/docs/Web/CSS/font-weight" target="_blank" title="The font-weight CSS property specifies the weight (or boldness) of the font. The font weights available to you will depend on the font-family you are using. Some fonts are only available in normal and bold."><code>font-weight</code></a></li>
     <li><a href="https://developer.mozilla.org/en-US/docs/Web/CSS/gap" target="_blank" title="The gap CSS property sets the gaps (gutters) between rows and columns. It is a shorthand for row-gap and column-gap."><code>gap</code></a></li>
     <li><a href="https://developer.mozilla.org/en-US/docs/Web/CSS/grid-column-gap" target="_blank" title="REDIRECT column-gap (grid-column-gap)"><code>grid-column-gap</code></a></li>
     <li><a href="https://developer.mozilla.org/en-US/docs/Web/CSS/grid-gap" target="_blank" title="REDIRECT gap (grid-gap)"><code>grid-gap</code></a></li>
     <li><a href="https://developer.mozilla.org/en-US/docs/Web/CSS/grid-row-gap" target="_blank" title="REDIRECT row-gap (grid-row-gap)"><code>grid-row-gap</code></a></li>
     <li><a href="https://developer.mozilla.org/en-US/docs/Web/CSS/height" target="_blank" title="The height CSS property specifies the height of an element. By default, the property defines the height of the content area. If box-sizing is set to border-box, however, it instead determines the height of the border area."><code>height</code></a></li>
     <li><a href="https://developer.mozilla.org/en-US/docs/Web/CSS/inset" target="_blank" title="The inset CSS property defines the logical block and inline start and end offsets of an element, which map to physical offsets depending on the element's writing mode, directionality, and text orientation. It corresponds to the top and bottom, or right and left properties depending on the values defined for writing-mode, direction, and text-orientation."><code>inset</code></a></li>
     <li><a href="https://developer.mozilla.org/en-US/docs/Web/CSS/inset-block" target="_blank" title="The inset-block CSS property defines the logical block start and end offsets of an element, which maps to physical offsets depending on the element's writing mode, directionality, and text orientation. It corresponds to the top and bottom, or right and left properties depending on the values defined for writing-mode, direction, and text-orientation."><code>inset-block</code></a></li>
     <li><a href="https://developer.mozilla.org/en-US/docs/Web/CSS/inset-block-end" target="_blank" title="The inset-block-end CSS property defines the logical block end offset of an element, which maps to a physical inset depending on the element's writing mode, directionality, and text orientation."><code>inset-block-end</code></a></li>
     <li><a href="https://developer.mozilla.org/en-US/docs/Web/CSS/inset-block-start" target="_blank" title="The inset-block-start CSS property defines the logical block start offset of an element, which maps to a physical inset depending on the element's writing mode, directionality, and text orientation."><code>inset-block-start</code></a></li>
     <li><a href="https://developer.mozilla.org/en-US/docs/Web/CSS/inset-inline" target="_blank" title="The inset-inline CSS property defines the logical block start and end offsets of an element, which maps to physical offsets depending on the element's writing mode, directionality, and text orientation. It corresponds to the top and bottom, or right and left properties depending on the values defined for writing-mode, direction, and text-orientation."><code>inset-inline</code></a></li>
     <li><a href="https://developer.mozilla.org/en-US/docs/Web/CSS/inset-inline-end" target="_blank" title="The inset-inline-end CSS property defines the logical inline end inset of an element, which maps to a physical inset depending on the element's writing mode, directionality, and text orientation."><code>inset-inline-end</code></a></li>
     <li><a href="https://developer.mozilla.org/en-US/docs/Web/CSS/inset-inline-start" target="_blank" title="The inset-inline-start CSS property defines the logical inline start inset of an element, which maps to a physical offset depending on the element's writing mode, directionality, and text orientation."><code>inset-inline-start</code></a></li>
     <li><a href="https://developer.mozilla.org/en-US/docs/Web/CSS/left" target="_blank" title="The left CSS property participates in specifying the horizontal position of a positioned element. It has no effect on non-positioned elements."><code>left</code></a></li>
     <li><a href="https://developer.mozilla.org/en-US/docs/Web/CSS/letter-spacing" target="_blank" title="The letter-spacing CSS property sets the spacing behavior between text characters."><code>letter-spacing</code></a></li>
     <li><a rel="nofollow" href="https://developer.mozilla.org/en-US/docs/Web/CSS/line-clamp" class="new" target="_blank" title="The documentation about this has not yet been written; please consider contributing!"><code>line-clamp</code></a></li>
     <li><a href="https://developer.mozilla.org/en-US/docs/Web/CSS/line-height" target="_blank" title="The line-height CSS property sets the amount of space used for lines, such as in text. On block-level elements, it specifies the minimum height of line boxes within the element. On non-replaced inline elements, it specifies the height that is used to calculate line box height."><code>line-height</code></a></li>
     <li><a href="https://developer.mozilla.org/en-US/docs/Web/CSS/margin" target="_blank" title="The margin CSS property sets the margin area on all four sides of an element. It is a shorthand for margin-top, margin-right, margin-bottom, and margin-left."><code>margin</code></a></li>
     <li><a href="https://developer.mozilla.org/en-US/docs/Web/CSS/margin-bottom" target="_blank" title="The margin-bottom CSS property sets the margin area on the bottom of an element. A positive value places it farther from its neighbors, while a negative value places it closer."><code>margin-bottom</code></a></li>
     <li><a href="https://developer.mozilla.org/en-US/docs/Web/CSS/margin-left" target="_blank" title="The margin-left CSS property sets the margin area on the left side of an element. A positive value places it farther from its neighbors, while a negative value places it closer."><code>margin-left</code></a></li>
     <li><a href="https://developer.mozilla.org/en-US/docs/Web/CSS/margin-right" target="_blank" title="The margin-right CSS property sets the margin area on the right side of an element. A positive value places it farther from its neighbors, while a negative value places it closer."><code>margin-right</code></a></li>
     <li><a href="https://developer.mozilla.org/en-US/docs/Web/CSS/margin-top" target="_blank" title="The margin-top CSS property sets the margin area on the top of an element. A positive value places it farther from its neighbors, while a negative value places it closer."><code>margin-top</code></a></li>
     <li><a href="https://developer.mozilla.org/en-US/docs/Web/CSS/mask" target="_blank" title="The mask CSS property hides an element (partially or fully) by masking or clipping the image at specific points."><code>mask</code></a></li>
     <li><a href="https://developer.mozilla.org/en-US/docs/Web/CSS/mask-border" target="_blank" title="The mask-border CSS property lets you create a mask along the edge of an element's border."><code>mask-border</code></a></li>
     <li><a href="https://developer.mozilla.org/en-US/docs/Web/CSS/mask-position" target="_blank" title="The mask-position CSS property sets the initial position, relative to the mask position layer set by mask-origin, for each defined mask image."><code>mask-position</code></a></li>
     <li><a href="https://developer.mozilla.org/en-US/docs/Web/CSS/mask-size" target="_blank" title="The mask-size CSS property specifies the sizes of the mask images. The size of the image can be fully or partially constrained in order to preserve its intrinsic ratio."><code>mask-size</code></a></li>
     <li><a href="https://developer.mozilla.org/en-US/docs/Web/CSS/max-height" target="_blank" title="The max-height CSS property sets the maximum height of an element. It prevents the used value of the height property from becoming larger than the value specified for max-height."><code>max-height</code></a></li>
     <li><a rel="nofollow" href="https://developer.mozilla.org/en-US/docs/Web/CSS/max-lines" class="new" target="_blank" title="The documentation about this has not yet been written; please consider contributing!"><code>max-lines</code></a></li>
     <li><a href="https://developer.mozilla.org/en-US/docs/Web/CSS/max-width" target="_blank" title="The max-width CSS property sets the maximum width of an element. It prevents the used value of the width property from becoming larger than the value specified by max-width."><code>max-width</code></a></li>
     <li><a href="https://developer.mozilla.org/en-US/docs/Web/CSS/min-height" target="_blank" title="The min-height CSS property sets the minimum height of an element. It prevents the used value of the height property from becoming smaller than the value specified for min-height."><code>min-height</code></a></li>
     <li><a href="https://developer.mozilla.org/en-US/docs/Web/CSS/min-width" target="_blank" title="The min-width CSS property sets the minimum width of an element. It prevents the used value of the width property from becoming smaller than the value specified for min-width."><code>min-width</code></a></li>
     <li><a href="https://developer.mozilla.org/en-US/docs/Web/CSS/object-position" target="_blank" title="The object-position CSS property specifies the alignment of the selected replaced element's contents within the element's box."><code>object-position</code></a></li>
     <li><a href="https://developer.mozilla.org/en-US/docs/Web/CSS/offset" target="_blank" title="The offset CSS property is a shorthand property for animating an element along a defined path."><code>offset</code></a></li>
     <li><a rel="nofollow" href="https://developer.mozilla.org/en-US/docs/Web/CSS/offset-anchor" class="new" target="_blank" title="The documentation about this has not yet been written; please consider contributing!"><code>offset-anchor</code></a></li>
     <li><a href="https://developer.mozilla.org/en-US/docs/Web/CSS/offset-distance" target="_blank" title="The offset-distance CSS property specifies a position along an offset-path."><code>offset-distance</code></a></li>
     <li><a href="https://developer.mozilla.org/en-US/docs/Web/CSS/offset-path" target="_blank" title="The offset-path CSS property specifies a motion path for an element to follow and defines the element's positioning within the parent container or SVG coordinate system."><code>offset-path</code></a></li>
     <li><a rel="nofollow" href="https://developer.mozilla.org/en-US/docs/Web/CSS/offset-position" class="new" target="_blank" title="The documentation about this has not yet been written; please consider contributing!"><code>offset-position</code></a></li>
     <li><a href="https://developer.mozilla.org/en-US/docs/Web/CSS/offset-rotate" target="_blank" title="The offset-rotate CSS property defines the direction of the element while positioning along the offset path."><code>offset-rotate</code></a></li>
     <li><a href="https://developer.mozilla.org/en-US/docs/Web/CSS/opacity" target="_blank" title="The opacity CSS property sets the opacity of an element. Opacity is the degree to which content behind an element is hidden, and is the opposite of transparency."><code>opacity</code></a></li>
     <li><a href="https://developer.mozilla.org/en-US/docs/Web/CSS/order" target="_blank" title="The order CSS property sets the order to lay out an item in a flex or grid container. Items in a container are sorted by ascending order value and then by their source code order."><code>order</code></a></li>
     <li><a href="https://developer.mozilla.org/en-US/docs/Web/CSS/outline" target="_blank" title="The outline CSS property is a shorthand to set various outline properties in a single declaration: outline-style, outline-width, and outline-color."><code>outline</code></a></li>
     <li><a href="https://developer.mozilla.org/en-US/docs/Web/CSS/outline-color" target="_blank" title="The outline-color CSS property sets the color of an element's outline."><code>outline-color</code></a></li>
     <li><a href="https://developer.mozilla.org/en-US/docs/Web/CSS/outline-offset" target="_blank" title="The outline-offset CSS property sets the amount of space between an outline and the edge or border of an element."><code>outline-offset</code></a></li>
     <li><a href="https://developer.mozilla.org/en-US/docs/Web/CSS/outline-width" target="_blank" title="The outline-width CSS property sets the thickness of an element's outline. An outline is a line that is drawn around an element, outside the border."><code>outline-width</code></a></li>
     <li><a href="https://developer.mozilla.org/en-US/docs/Web/CSS/padding" target="_blank" title="The padding CSS property sets the padding area on all four sides of an element. It is a shorthand for padding-top, padding-right, padding-bottom, and padding-left."><code>padding</code></a></li>
     <li><a href="https://developer.mozilla.org/en-US/docs/Web/CSS/padding-bottom" target="_blank" title="The padding-bottom CSS property sets the height of the padding area on the bottom of an element."><code>padding-bottom</code></a></li>
     <li><a href="https://developer.mozilla.org/en-US/docs/Web/CSS/padding-left" target="_blank" title="The padding-left CSS property sets the width of the padding area on the top of an element."><code>padding-left</code></a></li>
     <li><a href="https://developer.mozilla.org/en-US/docs/Web/CSS/padding-right" target="_blank" title="The padding-right CSS property sets the width of the padding area on the right of an element."><code>padding-right</code></a></li>
     <li><a href="https://developer.mozilla.org/en-US/docs/Web/CSS/padding-top" target="_blank" title="The padding-top CSS property sets the height of the padding area on the top of an element."><code>padding-top</code></a></li>
     <li><a href="https://developer.mozilla.org/en-US/docs/Web/CSS/perspective" target="_blank" title="The perspective CSS property determines the distance between the z=0 plane and the user in order to give a 3D-positioned element some perspective."><code>perspective</code></a></li>
     <li><a href="https://developer.mozilla.org/en-US/docs/Web/CSS/perspective-origin" target="_blank" title="The perspective-origin CSS property determines the position at which the viewer is looking. It is used as the vanishing point by the perspective property."><code>perspective-origin</code></a></li>
     <li><a href="https://developer.mozilla.org/en-US/docs/Web/CSS/right" target="_blank" title="The right CSS property participates in specifying the horizontal position of a positioned element. It has no effect on non-positioned elements."><code>right</code></a></li>
     <li><a href="https://developer.mozilla.org/en-US/docs/Web/CSS/rotate" target="_blank" title="The rotate CSS property allows you to specify rotation transforms individually and independently of the transform property. This maps better to typical user interface usage, and saves having to remember the exact order of transform functions to specify in the transform property."><code>rotate</code></a></li>
     <li><a href="https://developer.mozilla.org/en-US/docs/Web/CSS/row-gap" target="_blank" title="The row-gap CSS property sets the size of the gap (gutter) between an element's grid rows."><code>row-gap</code></a></li>
     <li><a href="https://developer.mozilla.org/en-US/docs/Web/CSS/scale" target="_blank" title="The scale CSS property allows you to specify scale transforms individually and independantly of the transform property. This maps better to typical user interface usage, and saves having to remember the exact order of transform functions to specify in the transform value."><code>scale</code></a></li>
     <li><a href="https://developer.mozilla.org/en-US/docs/Web/CSS/scroll-margin" target="_blank" title="The scroll-margin property is a shorthand property which sets all of the scroll-margin longhands, assigning values much like the margin property does for the margin-* longhands."><code>scroll-margin</code></a></li>
     <li><a href="https://developer.mozilla.org/en-US/docs/Web/CSS/scroll-margin-block" target="_blank" title="The scroll-margin-block property is a shorthand property which sets the scroll-margin longhands in the block dimension."><code>scroll-margin-block</code></a></li>
     <li><a href="https://developer.mozilla.org/en-US/docs/Web/CSS/scroll-margin-block-end" target="_blank" title="The scroll-margin-block-end property defines the margin of the scroll snap area at the end of the block dimension that is used for snapping this box to the snapport. The scroll snap area is determined by taking the transformed border box, finding its rectangular bounding box (axis-aligned in the scroll container’s coordinate space), then adding the specified outsets."><code>scroll-margin-block-end</code></a></li>
     <li><a href="https://developer.mozilla.org/en-US/docs/Web/CSS/scroll-margin-block-start" target="_blank" title="The scroll-margin-block-start property defines the margin of the scroll snap area at the start of the block dimension that is used for snapping this box to the snapport. The scroll snap area is determined by taking the transformed border box, finding its rectangular bounding box (axis-aligned in the scroll container’s coordinate space), then adding the specified outsets."><code>scroll-margin-block-start</code></a></li>
     <li><a href="https://developer.mozilla.org/en-US/docs/Web/CSS/scroll-margin-bottom" target="_blank" title="The scroll-margin-bottom property defines the bottom margin of the scroll snap area that is used for snapping this box to the snapport. The scroll snap area is determined by taking the transformed border box, finding its rectangular bounding box (axis-aligned in the scroll container’s coordinate space), then adding the specified outsets."><code>scroll-margin-bottom</code></a></li>
     <li><a href="https://developer.mozilla.org/en-US/docs/Web/CSS/scroll-margin-inline" target="_blank" title="The scroll-margin-inline property is a shorthand property which sets the scroll-margin longhands in the inline dimension."><code>scroll-margin-inline</code></a></li>
     <li><a href="https://developer.mozilla.org/en-US/docs/Web/CSS/scroll-margin-inline-end" target="_blank" title="The scroll-margin-inline-end property defines the margin of the scroll snap area at the end of the inline dimension that is used for snapping this box to the snapport. The scroll snap area is determined by taking the transformed border box, finding its rectangular bounding box (axis-aligned in the scroll container’s coordinate space), then adding the specified outsets."><code>scroll-margin-inline-end</code></a></li>
     <li><a href="https://developer.mozilla.org/en-US/docs/Web/CSS/scroll-margin-inline-start" target="_blank" title="The scroll-margin-inline-start property defines the margin of the scroll snap area at the start of the inline dimension that is used for snapping this box to the snapport. The scroll snap area is determined by taking the transformed border box, finding its rectangular bounding box (axis-aligned in the scroll container’s coordinate space), then adding the specified outsets."><code>scroll-margin-inline-start</code></a></li>
     <li><a href="https://developer.mozilla.org/en-US/docs/Web/CSS/scroll-margin-left" target="_blank" title="The scroll-margin-left property defines the left margin of the scroll snap area that is used for snapping this box to the snapport. The scroll snap area is determined by taking the transformed border box, finding its rectangular bounding box (axis-aligned in the scroll container’s coordinate space), then adding the specified outsets."><code>scroll-margin-left</code></a></li>
     <li><a href="https://developer.mozilla.org/en-US/docs/Web/CSS/scroll-margin-right" target="_blank" title="The scroll-margin-right property defines the right margin of the scroll snap area that is used for snapping this box to the snapport. The scroll snap area is determined by taking the transformed border box, finding its rectangular bounding box (axis-aligned in the scroll container’s coordinate space), then adding the specified outsets."><code>scroll-margin-right</code></a></li>
     <li><a href="https://developer.mozilla.org/en-US/docs/Web/CSS/scroll-margin-top" target="_blank" title="The scroll-margin-top property defines the top margin of the scroll snap area that is used for snapping this box to the snapport. The scroll snap area is determined by taking the transformed border box, finding its rectangular bounding box (axis-aligned in the scroll container’s coordinate space), then adding the specified outsets."><code>scroll-margin-top</code></a></li>
     <li><a href="https://developer.mozilla.org/en-US/docs/Web/CSS/scroll-padding" target="_blank" title="The scroll-padding property is a shorthand property which sets all of the scroll-padding longhands, assigning values much like the padding property does for the padding-* longhands.
 
 The scroll-padding properties define offsets for the optimal viewing region of the scrollport: the region used as the target region for placing things in view of the user. This allows the author to exclude regions of the scrollport that are obscured by other content (such as fixed-positioned toolbars or sidebars) or simply to put more breathing room between a targetted element and the edges of the scrollport."><code>scroll-padding</code></a></li>
     <li><a href="https://developer.mozilla.org/en-US/docs/Web/CSS/scroll-padding-block" target="_blank" title="The scroll-padding-block property is a shorthand property which sets the scroll-padding longhands for the block dimension. The scroll-padding properties define offsets for the optimal viewing region of the scrollport: the region used as the target region for placing things in view of the user. This allows the author to exclude regions of the scrollport that are obscured by other content (such as fixed-positioned toolbars or sidebars) or simply to put more breathing room between a targetted element and the edges of the scrollport."><code>scroll-padding-block</code></a></li>
     <li><a href="https://developer.mozilla.org/en-US/docs/Web/CSS/scroll-padding-block-end" target="_blank" title="The scroll-padding-block-end property defines offsets for the end edge in the block dimension of the optimal viewing region of the scrollport: the region used as the target region for placing things in view of the user. This allows the author to exclude regions of the scrollport that are obscured by other content (such as fixed-positioned toolbars or sidebars) or simply to put more breathing room between a targetted element and the edges of the scrollport."><code>scroll-padding-block-end</code></a></li>
     <li><a href="https://developer.mozilla.org/en-US/docs/Web/CSS/scroll-padding-block-start" target="_blank" title="The scroll-padding-block-start property defines offsets for the start edge in the block dimension of the optimal viewing region of the scrollport: the region used as the target region for placing things in view of the user. This allows the author to exclude regions of the scrollport that are obscured by other content (such as fixed-positioned toolbars or sidebars) or simply to put more breathing room between a targetted element and the edges of the scrollport."><code>scroll-padding-block-start</code></a></li>
     <li><a href="https://developer.mozilla.org/en-US/docs/Web/CSS/scroll-padding-bottom" target="_blank" title="The scroll-padding-bottom property defines offsets for the bottom of the optimal viewing region of the scrollport: the region used as the target region for placing things in view of the user. This allows the author to exclude regions of the scrollport that are obscured by other content (such as fixed-positioned toolbars or sidebars) or simply to put more breathing room between a targetted element and the edges of the scrollport."><code>scroll-padding-bottom</code></a></li>
     <li><a href="https://developer.mozilla.org/en-US/docs/Web/CSS/scroll-padding-inline" target="_blank" title="The scroll-padding-inline property is a shorthand property which sets the scroll-padding longhands for the inline dimension. 
 The scroll-padding properties define offsets for the optimal viewing region of the scrollport: the region used as the target region for placing things in view of the user. This allows the author to exclude regions of the scrollport that are obscured by other content (such as fixed-positioned toolbars or sidebars) or simply to put more breathing room between a targetted element and the edges of the scrollport."><code>scroll-padding-inline</code></a></li>
     <li><a href="https://developer.mozilla.org/en-US/docs/Web/CSS/scroll-padding-inline-end" target="_blank" title="The scroll-padding-inline-end property defines offsets for the end edge in the inline dimension of the optimal viewing region of the scrollport: the region used as the target region for placing things in view of the user. This allows the author to exclude regions of the scrollport that are obscured by other content (such as fixed-positioned toolbars or sidebars) or simply to put more breathing room between a targetted element and the edges of the scrollport."><code>scroll-padding-inline-end</code></a></li>
     <li><a href="https://developer.mozilla.org/en-US/docs/Web/CSS/scroll-padding-inline-start" target="_blank" title="The scroll-padding-inline-start property defines offsets for the start edge in the inline dimension of the optimal viewing region of the scrollport: the region used as the target region for placing things in view of the user. This allows the author to exclude regions of the scrollport that are obscured by other content (such as fixed-positioned toolbars or sidebars) or simply to put more breathing room between a targetted element and the edges of the scrollport."><code>scroll-padding-inline-start</code></a></li>
     <li><a href="https://developer.mozilla.org/en-US/docs/Web/CSS/scroll-padding-left" target="_blank" title="The scroll-padding-left property defines offsets for the left of the optimal viewing region of the scrollport: the region used as the target region for placing things in view of the user. This allows the author to exclude regions of the scrollport that are obscured by other content (such as fixed-positioned toolbars or sidebars) or simply to put more breathing room between a targetted element and the edges of the scrollport."><code>scroll-padding-left</code></a></li>
     <li><a href="https://developer.mozilla.org/en-US/docs/Web/CSS/scroll-padding-right" target="_blank" title="The scroll-padding-right property defines offsets for the right of the optimal viewing region of the scrollport: the region used as the target region for placing things in view of the user. This allows the author to exclude regions of the scrollport that are obscured by other content (such as fixed-positioned toolbars or sidebars) or simply to put more breathing room between a targetted element and the edges of the scrollport."><code>scroll-padding-right</code></a></li>
     <li><a href="https://developer.mozilla.org/en-US/docs/Web/CSS/scroll-padding-top" target="_blank" title="The scroll-padding-top property defines offsets for the top of the optimal viewing region of the scrollport: the region used as the target region for placing things in view of the user. This allows the author to exclude regions of the scrollport that are obscured by other content (such as fixed-positioned toolbars or sidebars) or simply to put more breathing room between a targetted element and the edges of the scrollport."><code>scroll-padding-top</code></a></li>
     <li><a href="https://developer.mozilla.org/en-US/docs/Web/CSS/scroll-snap-coordinate" target="_blank" title="The scroll-snap-coordinate CSS property defines the x and y coordinate positions within an element that will align with its nearest ancestor scroll container's scroll-snap-destination for each respective axis."><code>scroll-snap-coordinate</code></a></li>
     <li><a href="https://developer.mozilla.org/en-US/docs/Web/CSS/scroll-snap-destination" target="_blank" title="The scroll-snap-destination CSS property defines the position in x and y coordinates within the scroll container's visual viewport which element snap points align with."><code>scroll-snap-destination</code></a></li>
     <li><a href="https://developer.mozilla.org/en-US/docs/Web/CSS/scrollbar-color" target="_blank" title="The scrollbar-color CSS property sets the color of the scrollbar track and thumb."><code>scrollbar-color</code></a></li>
     <li><a href="https://developer.mozilla.org/en-US/docs/Web/CSS/shape-image-threshold" target="_blank" title="The shape-image-threshold CSS property sets the alpha channel threshold used to extract the shape using an image as the value for shape-outside."><code>shape-image-threshold</code></a></li>
     <li><a href="https://developer.mozilla.org/en-US/docs/Web/CSS/shape-margin" target="_blank" title="The shape-margin CSS property sets a margin for a CSS shape created using shape-outside."><code>shape-margin</code></a></li>
     <li><a href="https://developer.mozilla.org/en-US/docs/Web/CSS/shape-outside" target="_blank" title="The shape-outside CSS property defines a shape—which may be non-rectangular—around which adjacent inline content should wrap."><code>shape-outside</code></a></li>
     <li><a href="https://developer.mozilla.org/en-US/docs/Web/CSS/tab-size" target="_blank" title="The tab-size CSS property is used to customize the width of a tab (U+0009) character."><code>tab-size</code></a></li>
     <li><a href="https://developer.mozilla.org/en-US/docs/Web/CSS/text-decoration" target="_blank" title="The text-decoration CSS property sets the appearance of decorative lines on text. It is a shorthand for text-decoration-line, text-decoration-color, and text-decoration-style."><code>text-decoration</code></a></li>
     <li><a href="https://developer.mozilla.org/en-US/docs/Web/CSS/text-decoration-color" target="_blank" title="The text-decoration-color CSS property sets the color of decorations added to text by text-decoration-line."><code>text-decoration-color</code></a></li>
     <li><a href="https://developer.mozilla.org/en-US/docs/Web/CSS/text-emphasis" target="_blank" title="The text-emphasis CSS property applies emphasis marks to text (except spaces and control characters). It is a shorthand for text-emphasis-style and text-emphasis-color."><code>text-emphasis</code></a></li>
     <li><a href="https://developer.mozilla.org/en-US/docs/Web/CSS/text-emphasis-color" target="_blank" title="The text-emphasis-color CSS property sets the color of emphasis marks. This value can also be set using the text-emphasis shorthand."><code>text-emphasis-color</code></a></li>
     <li><a href="https://developer.mozilla.org/en-US/docs/Web/CSS/text-indent" target="_blank" title="The text-indent CSS property sets the length of empty space (indentation) that is put before lines of text in a block."><code>text-indent</code></a></li>
     <li><a href="https://developer.mozilla.org/en-US/docs/Web/CSS/text-shadow" target="_blank" title="The text-shadow CSS property adds shadows to text. It accepts a comma-separated list of shadows to be applied to the text and any of its decorations."><code>text-shadow</code></a></li>
     <li><a href="https://developer.mozilla.org/en-US/docs/Web/CSS/top" target="_blank" title="The top CSS property participates in specifying the vertical position of a positioned element. It has no effect on non-positioned elements."><code>top</code></a></li>
     <li><a href="https://developer.mozilla.org/en-US/docs/Web/CSS/transform" target="_blank" title="The transform CSS property lets you rotate, scale, skew, or translate an element. It modifies the coordinate space of the CSS visual formatting model."><code>transform</code></a></li>
     <li><a href="https://developer.mozilla.org/en-US/docs/Web/CSS/transform-origin" target="_blank" title="The transform-origin CSS property sets the origin for an element's transformations."><code>transform-origin</code></a></li>
     <li><a href="https://developer.mozilla.org/en-US/docs/Web/CSS/translate" target="_blank" title="The translate CSS property allows you to specify translation transforms individually and independantly of the transform property. This maps better to typical user interface usage, and saves having to remember the exact order of transform functions to specify in the transform value."><code>translate</code></a></li>
     <li><a href="https://developer.mozilla.org/en-US/docs/Web/CSS/vertical-align" target="_blank" title="The vertical-align CSS property sets vertical alignment of an inline or table-cell box."><code>vertical-align</code></a></li>
     <li><a href="https://developer.mozilla.org/en-US/docs/Web/CSS/visibility" target="_blank" title="The visibility CSS property shows or hides an element without changing the layout of a document. The property can also hide rows or columns in a &lt;table>."><code>visibility</code></a></li>
     <li><a href="https://developer.mozilla.org/en-US/docs/Web/CSS/width" target="_blank" title="The width CSS property sets an element's width. By default it sets the width of the content area, but if box-sizing is set to border-box, it sets the width of the border area."><code>width</code></a></li>
     <li><a href="https://developer.mozilla.org/en-US/docs/Web/CSS/word-spacing" target="_blank" title="The word-spacing CSS property sets the length of space between words and between tags."><code>word-spacing</code></a></li>
     <li><a href="https://developer.mozilla.org/en-US/docs/Web/CSS/z-index" target="_blank" title="The z-index CSS property sets the z-order of a positioned element and its descendants or flex items. Overlapping elements with a larger z-index cover those with a smaller one."><code>z-index</code></a></li>
     <li><a href="https://developer.mozilla.org/en-US/docs/Web/CSS/zoom" target="_blank" title="The non-standard zoom CSS property can be used to control the magnification level of an element."><code>zoom</code></a></li>
  </ul>




  Referencia: [developer.mozilla.org](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_animated_properties)
  
  
  [Volver al índice](#index)

<br>
<br>
<br>

# <a name="sec5">Web Animations API (Animaciones en JS)</a>

<br>
<br>

## <a name="clase17">element.animate</a>

Puedo hacer también animaciones con ```element.animate``` que es una propiedad de JavaScript.

    $element.animate()

Es una propiedad relativamente nueva y el soporte en los diferentes browsers no es todavía completo. 
Puedes ver la lista de compatibilidad [aquí](https://caniuse.com/#feat=web-animation).

### [La sintaxis](https://developer.mozilla.org/en-US/docs/Web/API/Web_Animations_API/Using_the_Web_Animations_API): 

Primero obtengo el elemento que quiero animar:

    const $element = document.getElementById('element')
  
Luego le agrego el método ```.animate()```:

    $element.animate()
    
```.animate()``` recibe dos objetos:

  + 1 - el objeto correspondiente al @keyframes:

```javascript

  let keyFrames = [
    // from
    { transform: 'rotate() translate()', color: '#xxxxxx' },
    // to
    { transform: 'rotate() translate()', color: '#jjjjjj' }
  ];

```

  + 2 - un objeto correspondiente a las propiedades de animación:
  
```javascript

  let animateProperties = {
      duration: ms // CSS == animation-duration
      delay: ms  // CSS == animation-delay
      direction: // CSS == animation-direction
      easing: // CSS == animation-timing-function - default == 'linear'
      interactions: // CSS == animation-iteration-count - Infinity != CSS infinite
      fill: // CSS == animation-fill-mode 
      iterationStart: 0 - 1 // nativo de JS - frame de comienzo de animación - 0.4 = 40%
      endDelay: ms, // nativo de JS - tiempo de espera hasta repetir animación
  }
  
```

Código completo:

```javascript

    $element.animate(
      keyFrames,
      animateProperties
    )

```
Notar que los dos objetos van separados por una ',' simple.

* No hace falta generar variables.


<br>

[Volver al índice](#index)

<br>
<br>
<br>

## <a name="clase18">Controlar Animaciones</a>

Podemos controlar el estado de la animación. Esto podemos hacerlo por medio de botones que disparen la función que queremos.
Los métodos que tenemos disponibles podemos verlos en la variable 'animate' en la consola.

Ej (tomando el ejemplo de la clase anterior):

```javascript

    const animation = $element.animate(
      keyFrames,
      animateProperties
    )

    const $playButton = document.getElementById('play')
    const $pauseButton = document.getElementById('pause')
    const $stopButton = document.getElementById('stop')
    const $reverseButton = document.getElementById('reverse')

    $playButton.addEventListener('click', (event) => {
      animation.play()
    })
    $pauseButton.addEventListener('click', (event) => {
      animation.pause()
    })
    $stopButton.addEventListener('click', (event) => {
      animation.cancel()
    })
    $reverseButton.addEventListener('click', (event) => {
      animation.reverse()
    })

```

[Volver al índice](#index)

<br>
<br>
<br>

## <a name="clase19">Estás listo para certificarte</a>

<br>

[Volver al índice](#index)

<br>
<br>
<br>

# <a name="sec7">Contenido bonus: Animaciones en ReactJS</a>

<br>
<br>

## <a name="clase29">Intro al proyecto final del curso</a>


<br>

[Volver al índice](#index)

<br>
<br>
<br>

## <a name="clase30">Configurando una aplicación en React JS</a>

ReactJS es una librería de JavaScript desarrollada por facebook basada en componentes.
En esta sección del curso aprenderemos a dominar una interfaz, crear componentes y a animarlos.
En el mundo de ECMAScript hay funciones no soportadas por todos los navegadores. Es sobre todo por este aspecto que utilizamos librerías y frameworks. 


### SetUp

Para crear una aplicación de ReacJS tengo que instalarlo primero para generar el entorno de desarrollo.
Esto lo hacemos con ```npm``` a travez del ```terminal``` por línea de comandos. 
[Aquí](https://facebook.github.io/create-react-app/) la documentación.

```
  npx create-react-app my-app
  
```
```
  cd my-app

```
```
  npm start 

```
React activa (crea/genera) un servidor local para nuestra aplicación y nos abre una ventana de bienvenida.






<br>

[Volver al índice](#index)

<br>
<br>
<br>

## <a name="clase31">Estructura de proyectos con React</a>

 Después de la instalación local y de iniciar ```npm``` revisando los archivos del nuevo proyecto creado, podemos ver que entre otros archivos ha creado una carpeta ```public``` y otra ```src```.

 En ```public``` se encuentra el archivo ```index.html``` que será el archivo que compile nuestro código dentro de su elemento ```<div id="root"></div>```.

 En ```src``` se encuentran los archivos sobre los que trabajaremos.
 
 + index.js - será el enlace con nuestra aplicación. Aquí se encuentra el componente _**App**_ y el import del archivo css, a demás del ```getElementById()``` que lo enlaza con el elemento **root** en ```index.html```.
 
index.js:

```react

  import React from 'react';
  import ReactDOM from 'react-dom';
  import './index.css';
  import App from './App';
  import * as serviceWorker from './serviceWorker';

  ReactDOM.render(<App />, document.getElementById('root'));

  // If you want your app to work offline and load faster, you can change
  // unregister() to register() below. Note this comes with some pitfalls.
  // Learn more about service workers: http://bit.ly/CRA-PWA
  serviceWorker.unregister();

```

React (línea 1) nos permite crear componentes. - ```<App />```
ReactDOM (línea 2) nos aporta el método ```.render()``` que introduce el componente generado ```<App />``` dentro del elemento ```getElementById('root')``` en ```index.html```.
Este _componente base_ ```<App />``` será donde iremos incorporando el nuevo arbol de componentes que vallamos generando para nuestro proyecto.
  
El ```index.css``` (import línea 3 de index.js) tiene estilos para el _body_. 
El archivo App.js (import en línea 4 de index.js) contiene el mismo _componente base_ a demás de la importación del archivo ```App.css``` que tiene los estilos propios del componente base. 
Una particularidad a notar en este archivo CSS es que los nombres de las clases comienzan con mayúsculas (.App), esto obedece una convención para escribir _componentes_ de JS, ya que al fin y al cabo los _componentes_ son clases (```class```) de JavaScript y estas deberían comenzar con mayúsculas. 

Otra convención es el hecho de nombrar las clases CSS como subclases del elemento padre anteponiendo el nombre de la clase más un guión medio antes del estilo del nuevo objeto html.


```html

      <div className="App">
        <header className="App-header">
          <img src={logo} className="App-logo" alt="logo" />
          <p className="App-paragraph1">
            Edit <code>src/App.js</code> and save to reload.
          </p>
          .
          .
          .

          
```

Archivo ```App.js```:


```js

  import React, { Component } from 'react';
  import logo from './logo.svg';
  import './App.css';

  class App extends Component {
    render() {
        return (
          <div className="App">
          .
          .
          .

```

 En línea 1 importo _React_ y _**{ Component }**_ que es un método dentro de _React_ nos va a permitir crear la clase _App_ (línea 5).

 Los elementos tienen un método principal que es _**render()**_. 
 _**render()**_ va a renderizar la UI de nuestro componente, o lo que podríamos llamar el código HTML de nuestro mismo componente pero que en ReactJS se llama propiamente [_**JSX**_](https://reactjs.org/docs/introducing-jsx.html).
 Este _**JSX**_ nos permite escribir código HTML y a demás introducir variables, objetos, mátodos y/o código JavaScript siempre que lo hagamos entre llaves.
 
  
        <img    src={logo}    className="App-logo" alt="logo" />
 
 
 Otro punto importante es cerrar siempre los tags simples de html como el ejemplo anterior que es una imagen. Si la pusieramos sin el 'slash' daría un error.
 
 Otro data particular es que el compilador de ```npm``` refresca automáticamente el browser cada vez que salvamos cambios en nuestro proyecto.
 
<br>

[Volver al índice](#index)

<br>
<br>
<br>

## <a name="clase32">Animaciones con React Transicion Group</a>

<br>

[Volver al índice](#index)

<br>
<br>
<br>

## <a name="clase33">Llevando HTML y CSS a React JS</a>

<br>

[Volver al índice](#index)

<br>
<br>
<br>

## <a name="clase34">Pasando de una página estática a una dinámica con propiedades</a>

<br>

[Volver al índice](#index)

<br>
<br>
<br>

## <a name="clase35">Puliendo el CSS de invie</a>


<br>

[Volver al índice](#index)

<br>
<br>
<br>

## <a name="clase36">Añadiendo Cheet JS</a>


<br>

[Volver al índice](#index)

<br>
<br>
<br>

## <a name="clase37">Configurando Redux</a>


<br>

[Volver al índice](#index)

<br>
<br>
<br>

## <a name="clase38">Animando las guitarras</a>


<br>

[Volver al índice](#index)

<br>
<br>
<br>

## <a name="clase39">Transición en los Cards de Guitarras</a>



<br>

[Volver al índice](#index)

<br>
<br>
<br>

## <a name="clase40">Animación de entrada y salida en la portada</a>



<br>

[Volver al índice](#index)

<br>
<br>
<br>

## <a name="clase41">Animando el background de la portada</a>



<br>

[Volver al índice](#index)

<br>
<br>
<br>

## <a name="clase42">Multiplicando y animando los corazones</a>


[Volver al índice](#index)

### [Cierre del Curso](#clase43)

