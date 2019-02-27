# <a name="title" > Curso de PostCSS </a>
#
# Index
#

## [Sección I - Introducción](#sec1)
### [01 - Bienvenida al Curso de PostCSS](#clase1)
### [02 - Instalación y uso del cliente de PostCSS](#clase2)
### [03 - Instalando y usando plugins en PostCSS](#clase3)

#

## [Sección II - NextCSS - El futuro de CSS](#sec2)
### [04 - Instalando CSSNext](#clase4)
### [05 - Los nuevos módulos de CSS](#clase5)
### [06 - Variables](#clase6)
### [07 - Operaciones matemáticas con CSS - CALC ](#clase7)
### [08 - Media Queries](#clase8)
### [09 - Imágenes retina con Post CSS - Image-set](#clase9)
### [10 - Colores](#clase10)
### [11 - Fuentes](#clase11)
### [12 - Selectores Personalizados](#clase12)
### [13 - Pseudo Clases](#clase13)
### [14 - Indentando (nesting)](#clase14)

#

## [Sección III - Plugins de PostCSS](#sec3)
### [15 - Modulariza tu código con postcss-Imports](#clase15)
### [16 - Auto font-face con FontMagician](#clase16)
### [17 - Validar CSS con Stylelint](#clase17)
### [18 - Agrupar Media Queries con mqpacker](#clase18)
### [19 - Optimiza CSS para producción con CSSNano](#clase19)
### [20 - Vocabulary for Marketing](#clase20)

#

## [Sección IV - Conclusiones](#sec4)
### [21 - Conclusiones del Curso de PostCSS](#clase21)

#

<br>
<br>
<br>

# <a name="sec1">Sección I - Introducción </a>

<br>
<br>

## <a name="clase1"> 01 - Bienvenida al Curso de PostCSS </a>

### Qué es postCSS?

PostCSS es una herramienta para transformar CSS con JavaScript. 
Es una herramienta construida en JavaScript que sirve para manipular los archivos de CSS y convertirlos en "un mejor CSS".

Existen nuevos features de CSS que no son todavía soportados por todos los navegadores.
PostCSS trabaja con features y sintaxis de CSS4 transpilando un archivo de código en CSS3 que todos los navegadores hasta la fecha puedan interpretar.






[To top...](https://github.com/pablojorgeandres/notas-clases/blob/master/postCSS.md#index)

<br>
<br>
<br>

## <a name="clase2"> 02 - Instalación y uso del cliente de PostCSS </a>

PostCSS puede utilizarse con WebPack, Gulp, Grunt o casi con cualquier administrador de entornos. 
También corre con su propio cliente.

Para instalar tenemos que tener seteado previamente node.js.
En terminal, voy a la carpeta del proyecto y:

    npm init

Se genera en la carpeta principal un archivo `package.json` con datos de nuestro proyecto.
Luego podemos instalar PostCSS.

    npm i postcss-cli --save

[Referencia aquí...](https://github.com/postcss/postcss-cli)

Se agrega entonces la dependencia. Podemos ver la versión en el `package.json` file.

```

    "dependencies": {
      "postcss-cli": "^6.1.2"
    }

```

Para invocar esta dependendencia local desde el terminal usamos `npx postcss` segido del comando que necesitemos:

```terminal

    npx postcss --version // imprime versión instalada
    
    
                                      /|\
                                    //   //
                                  //       //
                                //___*___*___//
                              //--*---------*--//
                            /|| *             * ||/
                          // ||*    v6.1.2     *|| //
                        //   || *             * ||   //
                      //_____||___*_________*___||_____//
                      

    
    npx postcss --help  // imprime comandos

      .
      .
      .
      
    Basic options:
      -o, --output   Output file                                            [string]
      -d, --dir      Output directory                                       [string]
      -r, --replace  Replace (overwrite) the input file                    [boolean]
      --map, -m      Create an external sourcemap
      --no-map       Disable the default inline sourcemaps
      --verbose      Be verbose                                            [boolean]
      --watch, -w    Watch files for changes and recompile as needed       [boolean]
      --env          A shortcut for setting NODE_ENV                        [string]
      
      .
      .
      .

```

Es posible crear scripts desde el `package.json` pero es realmente más agil para mantener un flujo de trabajo el hacerlo por línea de comandos.

Sobre todo lo que vamos a necesitar saber es cómo generar el archivo en el que se va a transpilar nuestro código CSS.
Este lo configuramos de la siguiente manera en terminal:

    npx postcss ruta/archivo/origen/style.css -o ruta/archivo/transpilado/style.css

Si quiero generar un archivo.css con otro nombre puedo hacerlo directamente en el comando anterior:

    npx postcss ruta/archivo/origen/style.css -o ruta/archivo/transpilado/otroNombre.css


Entonces , lo que ahora nuestro index invocará será el archivo transpilado. Hay que modificarlo en el <head>.

Si agrego un `-w` al final del comando anterior, npm quedará pendiente de los cambios que vallamos haciendo en el archivo e irá actualizando el transpilado cada vez que guardemos los cambios en nuestro archivo.css de origen.


[To top...](https://github.com/pablojorgeandres/notas-clases/blob/master/postCSS.md#index)

<br>
<br>
<br>

## <a name="clase3"> 03 - Instalando y usando plugins en PostCSS </a>

PostCSS es una herramienta para transformar CSS con JS y todo lo que hará es transpilar un archivo legible para multiples browsers a partir de los parámetros de los plugins que instalemos.

[Referencia plugins](https://www.postcss.parts/).

Podemos también generar nuestros plugins personales.

El primero que usaremos es **autoprefixer**. Este es el plugin más popular y existe desde antes de postCSS.
Lo que este plugin hace es agregar prefijos como -webkit- o -moz- por ejemplo a las propiedades de CSS siempre que sea necesario y los navegadores no soporten esa propiedad.

Para instalar:

        npm i --save autoprefixer

Se agrega entonces la dependencia. Podemos ver la versión en el `package.json` file.


```

      "dependencies": {
        "autoprefixer": "^9.4.9",
        "postcss-cli": "^6.1.2"
      }

```

Para utilizarlo hay dos formas.

  • De forma básica o por defecto a través del terminal con el comando `-u` después de `-w`:
  
    npx postcss src/css/home.css -o dist/css/home.css -w -u autoprefixer
    
  • De forma custom generando un archivo `postcss.config.js` en el root de nuestro proyecto.

   + carga por defecto

```javascript

        module.exports = {
            plugins: [
                require('autoprefixer')
            ]
        }


```
   + carga avanzada agregando prefijos para propiedades específicas de CSS:
   
```javascript


        module.exports = {
            plugins: [
                require('autoprefixer')({
                    grid: true
                })
            ]
        }


```

Como algo todavía más específico otra posibilidad es la de encender e interrumpir el mecanismo de generar prefijos por cada clase o id de css es nuestro `style.css` de origen.
[Ver documentación](https://github.com/postcss/autoprefixer) por propiedades ajustables.

Ej:

```CSS

        .a {
            transition: 1s; /* será prefixeada */
        }

        .b {
            /* autoprefixer: off */
            transition: 1s; /* no será prefixeada */
        }

        .c {
            /* autoprefixer: ignore next */
            transition: 1s; /* no será prefixeada */
            mask: url(image.png); /* será prefixeada */
        }


```


[To top...](https://github.com/pablojorgeandres/notas-clases/blob/master/postCSS.md#index)

<br>
<br>
<br>

# <a name="sec2">Sección II - NextCSS - El futuro de CSS</a>

<br>
<br>

## <a name="clase4"> 04 - Instalando CSSNext </a>



[To top...](https://github.com/pablojorgeandres/notas-clases/blob/master/postCSS.md#index)

<br>
<br>
<br>

## <a name="clase5"> 05 - Los nuevos módulos de CSS </a>



[To top...](https://github.com/pablojorgeandres/notas-clases/blob/master/postCSS.md#index)

<br>
<br>
<br>

## <a name="clase6"> 06 - Variables </a>



[To top...](https://github.com/pablojorgeandres/notas-clases/blob/master/postCSS.md#index)

<br>
<br>
<br>

## <a name="clase7"> 07 - Operaciones matemáticas con CSS - CALC </a>



[To top...](https://github.com/pablojorgeandres/notas-clases/blob/master/postCSS.md#index)

<br>
<br>
<br>

## <a name="clase8"> 08 - Media Queries </a>



[To top...](https://github.com/pablojorgeandres/notas-clases/blob/master/postCSS.md#index)

<br>
<br>
<br>

## <a name="clase9"> 09 - Imágenes retina con Post CSS - Image-set </a>



[To top...](https://github.com/pablojorgeandres/notas-clases/blob/master/postCSS.md#index)

<br>
<br>
<br>

## <a name="clase10"> 10 - Colores </a>



[To top...](https://github.com/pablojorgeandres/notas-clases/blob/master/postCSS.md#index)

<br>
<br>
<br>

## <a name="clase11"> 11 - Fuentes </a>



[To top...](https://github.com/pablojorgeandres/notas-clases/blob/master/postCSS.md#index)

<br>
<br>
<br>

## <a name="clase12"> 12 - Selectores Personalizados </a>



[To top...](https://github.com/pablojorgeandres/notas-clases/blob/master/postCSS.md#index)

<br>
<br>
<br>

## <a name="clase13"> 13 - Pseudo Clases </a>



[To top...](https://github.com/pablojorgeandres/notas-clases/blob/master/postCSS.md#index)

<br>
<br>
<br>

## <a name="clase14"> 14 - Indentando (nesting) </a>



[To top...](https://github.com/pablojorgeandres/notas-clases/blob/master/postCSS.md#index)

<br>
<br>
<br>

# <a name="sec3">Sección III - Plugins de PostCSS</a>

<br>
<br>

## <a name="clase15"> 15 - Modulariza tu código con postcss-Imports </a>



[To top...](https://github.com/pablojorgeandres/notas-clases/blob/master/postCSS.md#index)

<br>
<br>
<br>

## <a name="clase16"> 16 - Auto font-face con FontMagician </a>



[To top...](https://github.com/pablojorgeandres/notas-clases/blob/master/postCSS.md#index)

<br>
<br>
<br>

## <a name="clase17"> 17 - Validar CSS con Stylelint </a>



[To top...](https://github.com/pablojorgeandres/notas-clases/blob/master/postCSS.md#index)

<br>
<br>
<br>

## <a name="clase18"> 18 - Agrupar Media Queries con mqpacker </a>



[To top...](https://github.com/pablojorgeandres/notas-clases/blob/master/postCSS.md#index)

<br>
<br>
<br>

## <a name="clase19"> 19 - Optimiza CSS para producción con CSSNano </a>



[To top...](https://github.com/pablojorgeandres/notas-clases/blob/master/postCSS.md#index)

<br>
<br>
<br>

## <a name="clase20"> 20 - Vocabulary for Marketing </a>



[To top...](https://github.com/pablojorgeandres/notas-clases/blob/master/postCSS.md#index)

<br>
<br>
<br>

# <a name="sec4">Sección IV - Conclusiones</a>

<br>
<br>

## <a name="clase21"> 21 - Conclusiones del Curso de PostCSS </a>



[To top...](https://github.com/pablojorgeandres/notas-clases/blob/master/postCSS.md#index)

