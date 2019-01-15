# Índice

### [04 - Variables](#clase4)
### [05 - Variables - Strings](#clase5)
### [06 - Variables - Numbers](#clase6)
### [07 - Funciones](#clase7)
### [08 - Alcance de las Funciones](#clase8)
### [09 - Objetos](#clase9)    

<br>
<br>
<br>

# Resumen clase por clase:

<br>

## <a name="clase4"> 04 - Variables </a>


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

## <a name="clase5"> 05 - Variables - Strings </a>

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

## <a name="clase6"> 06 - Variables - Numbers </a>

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

## <a name="clase7"> 07 - Funciones </a>

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

## <a name="clase8"> 08 - Alcance de las Funciones </a>

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

Al definir una variable de forma global, se la asigna al objeto global.
En un servidor el contexto es por ejemplo node, en el browser el objeto global es 'window'. La variable 'nombre'en el ejemplo anterior queda asignada al objeto global 'window'.

```javascript

	window.nombre 
	// "SACHA"
	
```


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

## <a name="clase9"> 09 - Objetos </a>

Cómo declararlos, cuáles son sus ventajas, cómo asignarles atributos y cómo trabajar con ellos dentro de las funciones.

Los objetos se definen delimitados mediante llaves {}

	var objeto = {}

Un atributo se compone de una clave (key) y un valor (value), que se separan entre sí por dos puntos “”:"". 

	var yigit = {
		nombre: 'Yigit'
	}

Los valores pueden ser de tipo string, número, booleano, etc. Cada atributo está separado del siguiente por una coma. Un objeto puede tener todos los atributos que sean necesarios.

```javascript

	var yigit = {
		nombre: 'Yigit',
		apellido: 'Sultan'
		edad: 13
		...
	}
``` 

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

Las últimas versiones de JavaScript nos permiten desglosar el objeto dentro de los parámetros de la función. 
Lo hacemos pasando el _key_ del atributo entre "{}" dentro de los parámetros de la declaración de la función. 

```javascript

	function imprimirMayuscula({ nombre }){
		console.log(nombre.toUpperCase())
	}
	
	imprimirMayusculas(yigit)
	// YIGIT


```





