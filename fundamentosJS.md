# Índice

## [Primeros Pasos](#sec1)
### [03 - Variables](#clase3)
### [04 - Variables - Strings](#clase4)
### [05 - Variables - Numbers](#clase5)
### [06 - Funciones](#clase6)
### [07 - Alcance de las Funciones](#clase7)
### [08 - Objetos](#clase8)
### [09 - Desestructurar Objetos](#clase9)
### [10 - Parámetros como referencia o como valor](#clase10)
### [11 - Comparaciones en JavaScript](#Clase11)
## [Estructuras de Control y Funciones](#sec2)
### [12 - Condicionales](#clase12)
### [13 - Funciones que retornan valores](#clase13) 


<br>
<br>
<br>

# Resumen clase por clase:

<br>

# <a name="sec1"></a>Sección I - Primeros Pasos

## <a name="clase3"> 03 - Variables </a>


### Declaración:

Con el prefijo _'var'_ podemos crear una variable.

ej:

```javascript

    var nombre
    nombre = 'Aristóteles'
    var apellido = 'De Atenas'      //se puede declarar en una sóla linea

```

Otra forma:

```javascript

  var nombre = 'Tiglath', apellido = 'Azur'      // en la misma línea
  
  var nombre, apellido, edad
  
  nombre = 'Sherezade' 
  apellido = 'Efendi'
  edad = '24'

```   

 Javascript posee tipos de variables fácilmente intercambiables en la declaración de su valor. Esto significa que es un lenguaje debilmente tipeado. 
 Esto quiere decir que las variables declaradas pueden ser de cualquier tipo; string, number, boolean, etc. No conocemos exactamente el tipo de variables que estamos usando.
    
ej:

```javascript

    var peso = 75         // number
    var peso = '75Kgs'    // string

```

### Encadenar variables:

 Las variables en JS pueden encadenarse con otras variables y/o con texto con un signo '+'.

```javascript

    console.log('Mi nombre es ' + nombre + ' ' + apellido)

```

  También podemos usar comillas invertidas y escapar las variables entre ${}.

```javascript
  
    console.log(`Mi nombre es ${nombre} ${apellido}`)
    
```   

<br>
<br>
<br>

## <a name="clase4"> 04 - Variables - Strings </a>

Sobre una variable tipo string los métodos más básicos que podemos usar son:

	.toUpperCase() 	// convierte todo el string en mayúsculas
	.toLowerCase() 	// convierte todo el string en minúsculas
	.charAt(n)  	// nos dirige al caracter de la posición 'n'
	.length   	// arroja un número que equivale a la cantidad de caracteres del string 
	.substr(n, n1)  // arroja un string que comienza en la letra 'n' y termina en la letra 'n1' del string dado.

Ej:
	
```javascript

var nombre = 'Sacha', apellido = 'Lifszyc'

var nombreEnMayusculas = nombre.toUpperCase()  
// "SACHA"

var apellidoEnMinusculas = apellido.toLowerCase()   
// "lifszyc"

var primeraLetraDelNombre = nombre.charAt(0) 		
// "S"

var cantidadDeLetrasDelNombre = nombre.length    	
// 5

var nombreCompleto = `${nombre} ${apellido.toUpperCase()}`	
// también podemos acceder dentro de los escapes. Esta manera de concatenar se llama interpolación de texto.

var str = nombre.substr(1, 2)
// "ac"

```


<br>
<br>
<br>

## <a name="clase5"> 05 - Variables - Numbers </a>

Sobre una variable tipo _number_ los métodos básicos son:

	var += n 	// suma el valor agregado después de += a la variable
	var -= n 	// resta el valor agregado después de -= a la variable
	Math.round 	// redondea un floating-point number al integer más cercano
	toFixed(n)	// devuelve el valor mismo de la variable con 'n' dígitos después del '.' . La variable pasa de ser número a string
	parseFloat(var)	// convierte un string en un floating-point number

Ej:

```javascript

	var a = 10
	var b = 5

	a += 1 // a = a + 1
	// a = 11
	
	a -= 1  // a = a - 1
	// a = 10
	
	var c = a + b  
	// (Suma) c = 15
	
	c = a - b   
	// (Resta) c = 5
	
	var d = 200.3
	
	var e = a / b 
	// (División) e = 2

	d = d * 3 
	// (Multiplicación) d = 600.9000000000001 
	//javascript arroja siempre esta cantidad de números después de la ',' para números flotantes
	
	d = d * 100 * 3 / 100 
	// d = 600.9
	
	d = Math.round(d * 100 * 3 / 100) 
	// igual que sentencia anterior pero más preciso

	d = d.toFixed(2) 
	// d = "600.90" // Muestra 2 dígitos después de la coma.
	
	d = parseFloat(d)
	// d = 600.9


```

<br>
<br>
<br>

## <a name="clase6"> 06 - Funciones </a>

Las funciones son pedazos de código reutilizable.
Se declaran precedidas de la palabra clave 'function', van seguidas de un nombre para la función y lo que queremos que haga dentro de '{}'.

ej:
	function myFunction(){
		console.log('Hola Mundo!!!')
	}
	myFunction()
	// Hola Mundo!!!
	

Puedo agregar parámetros dentro de los paréntesis para hacer mi función dinámica.

ej:
	function myFunction(nombre) {
		console.log(`Hola ${nombre}.`)
	}
	myFunction('Walter')
	// Hola Walter.
	

<br>

Código de la clase:

```javascript

	var nombre = 'Sacha', edad = 28

	function imprimirEdad(n, e) {
	  console.log(`${n} tiene ${e} años`)
	}

	imprimirEdad(nombre, edad)
	imprimirEdad('Vicky', 28)
	imprimirEdad('Eric', 24)
	imprimirEdad('Darío', 27)
	imprimirEdad(25, 'Carlos')
	imprimirEdad('Juan')

```


<br>
<br>
<br>

## <a name="clase7"> 07 - Alcance de las Funciones </a>

  A qué variables puede acceder una función y qué valores van a tener esas variables al momento de invocar una función.

  Si una variable no está definida dentro de una función es de alcance global; es decir, se puede acceder a esta desde cualquier función. 

```javascript

	var nombre = 'Sacha'// global 

	functionnombreMayuscula(){
		nombre = nombre.toUpperCase() 
		console.log(nombre)
	}

	nombreMayuscula()
	// Esta función modofica la variable.

```

<br>

Al definir una variable de forma global, se la asigna al objeto global.
En un servidor el contexto es por ejemplo node, en el browser el objeto global es 'window'. La variable 'nombre'en el ejemplo anterior queda asignada al objeto global 'window'.

```javascript

	window.nombre 
	// "SACHA"
	
```

<br>

Es buena práctica que las funciones no modifiquen variables que no están dentro de ellas misma.
Para esto podemos usar los parámetros en las funciones.


```javascript

	functionnombreMayuscula(n){
		n = n.toUpperCase() 
		console.log(n)
	}

	nombreMayuscula('Juan') 
	// "JUAN"

```

<br>

También podemos usar específicamente la variable 'nombre' aunque la hayamos ya definido anteriormente, es decir que las variables como parámetros dentro de una función no modificarán las variables definidas por fuera de ellas con el mismo nombre.


```javascript

	functionnombreMayuscula( nombre ){
		nombre = nombre.toUpperCase() 
		console.log(nombre)
	}

	nombreMayuscula()

```



<br>
<br>
<br>

## <a name="clase8"> 08 - Objetos </a>

Cómo declararlos, cuáles son sus ventajas, cómo asignarles atributos y cómo trabajar con ellos dentro de las funciones.

Los objetos se definen delimitados mediante llaves {}

	var objeto = {}

<br>

Un atributo se compone de una clave (key) y un valor (value), que se separan entre sí por dos puntos “”:"". 

	var yigit = {
		nombre: 'Yigit'
	}

<br>

Los valores pueden ser de tipo string, número, booleano, etc. Cada atributo está separado del siguiente por una coma. Un objeto puede tener todos los atributos que sean necesarios.

```javascript

	var yigit = {
		nombre: 'Yigit',
		apellido: 'Sultan'
		edad: 13
		...
	}
``` 

<br>

Escribir el nombre de un objeto separado por un punto del nombre de un atributo, nos permite acceder al valor de dicho atributo para ese objeto. Un objeto también se puede pasar como atributo en una función.

```javascript

	yigit.nombre
	// "Yigit"
	
	function imprimirMayuscula(persona){
		console.log(persona.nombre.toUpperCase())
	}
	
	imprimirMayuscula(yigit)
	// YIGIT

```

<br>

Las últimas versiones de JavaScript nos permiten desglosar el objeto dentro de los parámetros de la función. 
Lo hacemos pasando el _key_ del atributo entre "{}" dentro de los parámetros de la declaración de la función. 

```javascript

	function imprimirMayuscula({ nombre }){
		console.log(nombre.toUpperCase())
	}
	
	imprimirMayusculas(yigit)
	// YIGIT


```

<br>
<br>
<br>

## <a name="clase09"> 09 - Desestructurar Objetos </a>

Otra forma de acceder a los atributos de los objetos es la desestructurización de los mismos.
Para no duplicar las variables, introducir como nombre de la variable el parámetro de la segunda variable entre '{}'. 

Ej:

```javascript
	
	var yigit = {
		nombre: 'Yigit',
		apellido: 'Sultan'
	}

	function imprimirMayuscula(persona){
		var { nombre } = persona  // var nombre = persona.nombre
		console.log(nombre.toUpperCase())
	}
	
	imprimirMayuscula(yigit)
	// YIGIT
	
```


<br>
<br>
<br>

## <a name="clase10"> 10 - Parámetros como referencia o como valor </a>

Javascript se comporta de manera distinta cuando le pasamos un objeto como parámetro.

Cuando los objetos se pasan como una referencia, estos serán modificados dentro y fuera de la función.

```javascript

	var sacha = {
		nombre: 'Sacha',
		apellido: 'Lifszyc',
		edad: 28
	}

	functioncumpleanos(persona) {
		persona.edad += 1
	} // esta función modifica el objeto
	
	sacha
	// { nombre: 'Sacha', apellido: 'Lifszyc', edad: 29 }

```

<br>


Para solucionar esto se puede crear un objeto diferente. 
Esto lo podemos hacer colocando tres puntos antes del nombre del parámetro al declarar la función.

La siguiente función copia el objeto (en la línea ...persona) y genera uno nuevo:

```javascript

	function cumpleanosOtro(persona) {
		return {
			...persona,
			edad: persona.edad + 1
		}
	}

	cumpleanosOtro(sacha) 
	// { nombre: 'Sacha', apellido: 'Lifszyc', edad: 29 }
	
	sacha
	// { nombre: 'Sacha', apellido: 'Lifszyc', edad: 28 }
	
```

<br>
<br>
<br>

## <a name="clase11"> 11 - Comparaciones en JavaScript</a>

Existen varias maneras de comparar variables u objetos dentro de javascript.

Existen cinco tipos de datos que son primitivos y es necesario comprender al momento de hacer comparaciones:

	• Boolean
	• Null
	• Undefined
	• Number
	• String

<br>

#### Variables

En el primer ejemplo le asignamos a _'x'_ un valor numérico y a _'y'_ un string. 
Para poder compararlos debemos agregar dos signos de igual "==". Esto los _convierte al mismo tipo de valor_ y permite que se puedan comparar.

```javascript

	var x = 4
	var y = '4'

	x == y    
	// true
	
```
<br>

Cuando realizamos operaciones es recomendable usar tres símbolos de igual (===). Esto permite que JavasScript no iguale las variables que son de distinto tipo. 

						*Sacha recomienda usa siempre el triple igual, pero hay controversia...


```javascript

	x === y  
	// false

```

#### Objetos

Al comparar objetos JS tiene en cuenta también el nombre del objeto, por lo tanto se remite a comparar el nombre de las variables a demás del valor de los atributos.
Con objetos literales desglosados (_otroMas_ en este caso), pasa lo mismo y la comparación da false ya que lo que se genera es un nuevo objeto a partir del desglosado.
 

```javascript

	var sacha = {
		nombre: 'Sacha'
	}
	var otro = {
		nombre: 'Sacha'
	}
	var otroMas = {
		...sacha
	}
	
	sacha == otro		
	// false
	
	sacha === otro 	
	// false

	sacha == otroMas	
	// false
	
	sacha === otroMas	
	// false

```

<br>

Si asignamos el valor del objeto a una variable y los comparamos, el doble y el triple igual darán como resultado ‘true’ ya que en este caso las dos variables estarían refiriendo al mismo espacio en la memoria RAM.

```javascript

	var otroMasTodavia = sacha

	sacha == otroMasTodavia	
	// True
	
	sacha === otroMasTodavia	
	// True

```


Otra cosa a tener en cuenta es que si cambiamos el valor del atributo en la variable, automáticamente cambia el valor del objeto también, por el mismo motivo que los operadores dan ‘true’, ambos refieren al mismo espacio en la memoria RAM.


```javascript

	otroMasTodavia.nombre = "Pepe"
	
	otroMasTodavia.nombre
	// "Pepe"
	
	sacha.nombre
	// "Pepe"

```


<br>
<br>
<br>
# <a name="sec2"></a>Sección II - Estructuras de Control y Funciones
<br>
<br>

## <a name="clase12"> 12 - Condicionales</a>

Las estructuras de control nos permiten controlar el flujo de nuestro código.
Algunas de ellas son:

  • if...else
  • switch
  • while
  • for
  • for...in
  • try

Los condicionales (_if...else_) nos permiten decidir si un código se ejecuta o no. Mediante un condicional (if) decidiremos si se ejecuta una parte de nuestro código cuando se cumpla o no cierta condición.

```javascript

	var sacha = {
		nombre: 'Sacha',
		apellido: 'Lifszyc',
		edad: 28,
		ingeniero: true,
		cocinero: false,
		cantante: false,
		dj: false,
		guitarrista: false,
		drone: true
	}

	function imprimirProfesion(persona) {
		console.log(`${persona.nombre} ${persona.apellido} es: `)
		if(persona.ingeniero) {
			console.log('Ingeniero')
		} else {
			console.log('No es Ingeniero')
		}
		if(persona.cocinero) {
			console.log('Cocinero')
		}
		if(persona.cantante) {
			console.log('Cantante')
		}
		if(persona.dj) {
			console.log('dj')
		}
		if(persona.guitarrista) {
			console.log('Guitarrista')
		}
		if(persona.drone) {
			console.log('Piloto de Drone')
		}
	}

```
<br>
<br>
<br>

## <a name="clase13"> 13 - Funciones que retornan valores </a>

