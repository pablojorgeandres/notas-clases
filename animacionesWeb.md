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

[_Transform_](#https://www.w3schools.com/cssref/css3_pr_transform.asp) es una propiedad muy utilizada en CSS3.
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

<br>
<br>
<br>

## <a name="clase7">Transformaciones de translación y perspectiva</a>

<br>
<br>
<br>

## <a name="clase8">Transformaciones de escala</a>

<br>
<br>
<br>

## <a name="clase9">Transformaciones de sesgado</a>

<br>
<br>
<br>

## <a name="clase10">Punto de transformación</a>



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

