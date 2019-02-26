Por qué index.html?

https://desarrolloweb.com/articulos/documento-por-defecto.html


# Resumen - video 2

## Cómo se construye una página web?

**Frontend   -   Backend**

**Frontend:** La parte visible para el cliente de un sitio web o un web app. 
**Backend:** La parte invisible para el cliente de un sitio web. Conexión entre back y front, bases de datos, procesos de servidor, host, url, etc. 
	CRUD - Create - Read - Update - Delete (funciones básicas del backend)

**HTML - CSS - JS**

**HTML:** HyperText Markup Language - sistema de texto tageado que permite estructurar las páginas web. 

	<body>
		<div>
		</div>
	</body>

**CSS:** Cascading Style Sheet - código para dar estilo, color, tamaños, espaciados y animaciones a las páginas web.

	body{
		margin: 0;
	}

**JS:** JavaScript - código de programación para agregar interacción de las páginas webs con el usuario. Manipulación de datos (variables) en el front, animaciones complejas, etc.

	document.getElementById(‘id')


____________________________________________________

# Resumen - video 4

**Qué es internet?**
Es un conjunto descentralizado de redes de comunicación interconectadas.
Muchas computadoras que se conectan entre sí.

**Protocolos**
Conjunto de reglas que posibilitan la comunicación en internet entre todo tipo de dispositivos.

**WWW:** World Wide Web, es uno y el más conocido y usado de los protocolos de internet.
Es un sistema de distribución de documentos de hipertexto interconectados y accesibles vía internet.

**Hypertexto:** texto que contiene enlaces a otros textos.

**FTP:** Transferenca de archivos entre sistemas conectados a una red.

## Tipos de dispositivos conectados a una red:

**Servidor:** computadora que contiene datos o archivos para ser consultados
**Cliente:** computadora o dispositivos de usuarios que consultan esos datos o archivos.

**P2P:** Peer to Peer - Todos conocemos el Torret, no? =D

**Tecnología de la información:** Es la aplicación de equipos de telecomunicación para almacenar, recuperar, transmitir y manipular datos, con frecuencia utilizado en el contexto de los negocios o empresas.
Información rápida e instantanea para resolver problemas de forma automática.
Las peticiones van a los servidores (en Alaska =).

## Tipos de comunicación:

**Síncrona y Asíncrona**

**Síncrona:**  comunicación en tiempo real. Ej video chat.

**Asíncrona:** comunicación en tiempo no real. Ej un email.

____________________________________________________


# Resumen - video 5

## Cómo funciona HTML

HTML es un tipo de Markup Language. 
**HyperText Markup Language**

Un sistema de hipertexto que se enfoca en la diferenciación y síntesis en un texto con etiquetas.

Estructura básica:

<html>
<header></header>
<body></body>
</html>

The <html> tag tells the browser that this is an HTML document.

The <html> tag represents the root of an HTML document.

The <html> tag is the container for all other HTML elements (except for the <!DOCTYPE> tag).



**Etiquetas comunes:**

Títulos encabezados:

<h1></h1>
<h2></h2>
<h3></h3>

Crear secciones o agrupar contenido:

<div></div>

Para crear párrafos:

<p></p>

Para determinar una sección definida:

<footer></footer>


____________________________________________________

# Resumen - video 6

## Etiquetas y sus atributos

**Etiquetas:** las etiquetas son fragmentos de texto rodeados por corchetes angulares (<  >) con funciones y usos específicos. Marcan un _comienzo_ y un _fin_ y en el medio se coloca el contenido formateado por la misma etiqueta. 

	inicio     contenido            fin
	<h1>   Este es un título  </h1>
Las etiquetas pueden contener **_Atributos_**
 **Atributos:** afectan al elemento por su presencia o enriquecen la definición de la misma.

Existen también las etiquetas meta o _"meta tags”_.
Estas se incorporan en el encabezado de una página web. 
Son información útil para navegadores y otros, mientras son invisibles para los clientes. 
Por ej. Los robots de google se valen de esta información para indexar sitios.

	<head> 
		<meta name=""description"" content=""Descripción de nuestra página"”> 
	</head>

Etiquetas comunes:

	<footer></footer> 					// sección específica
	<div></div> 						// secciones
	<span></span> 					// texto sin formato
	<img src=“image.png” alt=“Image” > 	//imágenes
	<a href=“platzi.com” >link</a> 		// links
	<meta charset=“UTF-8”>			// caracteres especiales

Aquí está el [link](https://developer.mozilla.org/es/docs/HTML/HTML5/HTML5_lista_elementos) a la lista de HTML5 tags.


_______________________________________________________________________

# Resumen - video 9

## Cómo funciona CSS

**[CSS](https://es.wikipedia.org/wiki/Hoja_de_estilos_en_cascada ):** Cascading Style Sheet - Hojas de Estilo en Cascada

Definen la apariencia de un documento HTML.

Para que nuestros estilos CSS se apliquen correctamente a nuestras páginas web, debemos utilizar la etiqueta link con el atributo href y la ruta a nuestro archivo .css:

```HTML
	
	<html> 
		<head> 
			<link rel=""stylesheet" href="estilos.css”">
		</head> 
		<body> 
			 ... etc ... etc…. 
		</body> 
	</html>


```

Se llaman “Estilos en Cascada” porque precisamente este nombre alude al funcionamiento estructural del lenguaje y cómo es interpretado por el browser. Siempre se lee en cascada, de arriba hacia abajo (+ abajo o más cerca del elemento, más importante) y se hereda hacia "objetos hijos”.


**Selectores** 
Los selectores son _**palabras claves**_ que CSS utiliza para apuntar a los elementos de HTML que contengan esa  _**palabra clave**_ como un atributo _**class**_ o _**id**_ en su tag. 
Respetando ciertas convenciones entre programadores, puedo darle a los _class_ o _id_ el nombre que quiera siempre que se respete el mismo para el mismo elemento tanto en el código CSS como en el HTML, de otra manera no funcionaría.


Ej **class**:

```css
	
.box{
	margin: 0;	
 }


```

```html
	
	<div class=“box” >
		<h1>Some Title</h1>
	 </div>


```

El selector **class** se declara con un “.” previo al keyword en el código CSS y entre comillas y sin punto precedente en el código HTML.

Ej **id**:

```css

 	#box{
		margin: 0;
 	}

```

```html

 	<div id=“box”>
		<h1>Some Title</h1>
	 </div>


```

El selector **id** se declara con un “#” previo al keyword en el código CSS y entre comillas y sin “#”  precedente en el código HTML. 

El **id** sólo puede apuntar a un elemento único dentro del DOM.

Dentro de los selectores en el documento CSS entre “{}” se definen los estilos de acuerdo a las **propiedades**.
Existen propiedades de ancho, alto, margen, relleno, color, etc.


Sintaxis en CSS:

```CSS
	
	body{
		background-color: rgb(0,0,0);      // define un background negro
	}


```

El código CSS puede usarse en los tags HTML con el atributo **style**, dentro del <head> de un documento HTML dentro de la etiqueta **<style>**, o desde un documento remoto con formato y extensión “.css” invocado en el <head> de un documento HTML con la etiqueta <link>.

Sintaxis:

Atributo **style**:

```HTML

	<div style=“width: 100px; height: 50px; background-color: black; color: white” >
		some content
	</div>
	
```


Etiqueta **<style>**:

```HTML
	
	<html>
		<head>
			<style>
				body {
					color: red;
				 }
			</style>
		</head>
		<body>
			...

```

Etiqueta <link>: (uso recomendado - buenas prácticas)

```HTML
	
	<html>
		<head>
			<link rel="stylesheet" href="style.css”>
		</head>
		<body>
			...

```

_______________________________________________________________

# Resumen video 10

## Cómo funciona JavaScript

JavaScript es un lenguaje de programación que nos permite realizar actividades complejas en nuestras páginas web: almacenar valores en variables o realizar operaciones.

DOM: Document Object Model - Modelo de los objetos de un documento HTML
JavaScript tiene la capacidad de modificar, crear o eliminar elementos dentro de un documento HTML.
Se dice que el DOM es el “arbol” con los elementos del documento HTML.

```HTML
	
	DOM
		HTML
			head
				links
				metas
			body
				div1
				div2
				…

```

El código javascript puede incluirse en un documento HTML dentro de un atributo de evento como "onclick" o “onhover”. ([HTML Event Attributes list](https://www.w3schools.com/tags/ref_eventattributes.asp ))

```HTML
	
	<div onmouseover=“alert(‘You are over me! Please don’t do that!')” ></div>

```

Dentro de la etiqueta **<script>**:

```HTML

	...
	</div>
	<script>
		console.log(’This message will appear at the console’)
	</script>
	<div>
	...

```

O en un tag <script src="script/script.js"></script> para invocar un documento externo con código JS (conviene antes de cerrar la etiqueta body).



________________________________________________________________________


# Resumen - video 12

## Paper wireframe

Qué queremos hacer?

Primero comunicamos nuestro producto.
Procuramos tener los CTA (call to action o los botones) visibles para el usuario.

Agregamos el logo en la esquina superior izquierda, ya que la visualización de los usuarios es en la diagonal de izquierda a derecha de arriba hacia abajo.
Los elemento principales deberíamos ponerlos en esa línea.

Sólo agrego los elementos que se que voy a usar efectivamente en el sitio.

Lo importante es que hagas un “Paper Wireframe” rápido, en menos de 10 minutos, si no, no vale la pena que hagas uno.

Me pongo en el lugar del usuario.



_________________________________________________________________________


# Resumen - video 14

## Diseño de interfaces con XD

Una vez listo el Paper Wireframe puedo pasar el diseño a digital en un programa de edición. Esta es la instancia previa a la maquetación así que debe ser lo más exacta posible.

Lo primero y básico, a demás de importante es definir us set de colores antes de comenzar a diseñar. Esto nos dará una “plantilla” para utilizar colores uniformes.
También se pueden definir tamaños, fuentes, etc.

En XD puedo generar “Symbols”  a partir de varios elementos para así poder reproducirlos idénticos en cualquier parte del diseño.
En la pestaña “prototype” de XD puedo generar links entre páginas del documento. (Cmd + enter para probar).


___________________________________________________________________________


# Resumen video 18
## Fuentes personalizadas y variables de CSS

```CSS

	:root{
		—green-1: green;
		—green-2: #454345;
		—width-1: 100px;
		—width-2: 200px;
	 }
	body {
		background: var(—green-1);
	 }

```
	

___________________________________________________________________________

# Resumen video 21

## Reglas responsive

Responsive Design consiste en crear estilos que se adapten a cualquier tamaño y posición de nuestros dispositivos electrónicos. Para esto, la mayoría de elementos organizados horizontalmente deben pasar a organizarse verticalmente.

La forma de añadir código CSS que se ejecute para tamaños de pantalla específicos es la siguiente:

@media (max-width: 600px) { /* 600px es solo un ejemplo */
        /* Todos nuestros estilos responsive */
}



_______________________________________________________________________________

# Resumen video 22

## Animaciones y transiciones

Animation es una propiedad de CSS3 para generar animaciones con CSS.

En la sintaxis, es indispensable agregar un **animation-duration** y un **animation-name** al elemento que queremos animar para que la animación funcione.
Luego con el keyword **@keyframes** y el nombre se la animación veteado en **animation-name** generamos la animación con los keywords **from{}** y **to{}**. También puede usarse %.
Dentro de los {} se agrega la propiedad CSS que se desea animar.
Para hacerlas funcionales en la mayoría de los browsers copiamos las propiedades **animation-duration** y **animation-name** con el prefijo **-webkit-**.
Lista de propiedades animables [aquí](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_animated_properties).

Ej: 

```CSS

	.fade-in{
		animation-name: fadein;
		-webkit-animation-name: fadein;
		animation-duration: 2s;
		-webkit-animation-duration: 2s;
	 }
	@keyframes fadein {
		from{
			opacity: 0;
		 }
		to{
			opacity: 1;
		 }
	}


```

__________________________________________________________________________________


# Resumen video 23

## Librería vs Framework

**Framework**
  Un framework es un marco de trabajo para hacer más rápido el trabajo.
  Se puede decir que es un molde a partir del cual puedo generar elementos con la misma base e ir modificándolos.

  Ej: Bootstrap - Foundation

**Librería**
Conjunto de rutinas, funciones que tiene un objetivo.
En general ahorran código o automatizan ciertas partes del mismo.


___________________________________________________________________________________













 
