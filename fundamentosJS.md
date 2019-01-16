# Índice

## [Sección I - Primeros Pasos](#sec1)
### [03 - Variables](#clase3)
### [04 - Variables - Strings](#clase4)
### [05 - Variables - Numbers](#clase5)
### [06 - Funciones](#clase6)
### [07 - Alcance de las Funciones](#clase7)
### [08 - Objetos](#clase8)
### [09 - Desestructurar Objetos](#clase9)
### [10 - Parámetros como referencia o como valor](#clase10)
### [11 - Comparaciones en JavaScript](#Clase11)

# 

## [Sección II - Estructuras de Control y Funciones](#sec2)
### [12 - Condicionales](#clase12)
### [13 - Funciones que retornan valores](#clase13)
### [14 - Arrow Functions](#clase14)
### [15 - Estructuras repetitivas: for...](#clase15)
### [16 - Estructuras repetitivas: while...](#clase16)
### [17 - Estructuras repetitivas: do while...](#clase17)
### [18 - Condicional Múltiple: switch ](#clase18)

# 

## [Sección III - Arrays](#sec3)
### [19 - Introducción a los Arrays](#clase19)
### [20 - Filtrar un array](#clase20)
### [21 - Transformar un array](#clase21)
### [22 - Reducir un array a un valor](#clase22)

# 

## [Sección IV - Programación Orientada a Objetos en JavaScript (POO)](#sec4)
### [23 - Como funcionan las clases en JavaScript](#clase23)
### [24 - Modificando un prototipo](#clase24)
### [25 - El contexto de las funciones: Quién es _this_?](#clase25)
### [26 - La verdad oculta sobre las clases en JavaScript](#clase26)
### [27 - Clases en JavaScript](#clase27)

#

## [Sección V - Asincronismo](#sec5)
### [28 - Funciones como parámetros](#clase28)
### [29 - Cómo funciona el asincronismo en JavaScript](#clase29)
### [30 - Cómo funciona el tiempo en JavaScript](#clase30)
### [31 - Callbacks](#clase31)
### [32 - Haciendo múltiples requests](#clase32)
### [33 - Manejando el Orden y el Asincronismo en JavaScript](#clase33)
### [34 - Manejo de errores con callbacks](#clase34)
### [35 - Promesas](#clase35)
### [36 - Promesas Encadenadas](#clase36)
### [37 - Múltiples promesas en paralelo](#clase37)
### [38 - Async-await: lo último en asincronismo](#clase38)

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

Usamos condicionales para desglosar las funciones en funciones más pequeñas que retornen un valor.

Return detiene la ejecución de una función y devuelve el valor de esa función.

Las variables definidas con _'const'_ se comportan como las variables _'var'_, excepto que no pueden ser reasignadas. Las constantes pueden ser declaradas en mayúsculas o minúsculas. Pero por convención, para distinguirlas del resto de variables, se escribe todo en mayusculas.



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

	const MAYORIA_DE_EDAD = 18

	functionesMayorDeEdad(persona) {
		return persona.edad >= MAYORIA_DE_EDAD
	}

	functionimprimirSiEsMayorDeEdad(persona) {
		if(esMayorDeEdad(persona)) {
			console.log(`${persona.nombre}${persona.apellido} es mayor de edad.`)
		} else {
			console.log(`${persona.nombre}${persona.apellido} no es mayor de edad.`)		
		}
	}

```


<br>
<br>
<br>

## <a name="clase14"> 14 - Arrow Functions </a>

Loas Arrow Functions permiten una nomenclatura más corta para escribir expresiones de funciones. 

Este tipo de funciones deben definirse antes de ser utilizadas.

Al escribir las Arrow Functions no es necesario escribir la palabra function, la palabra return, ni las llaves.


JS permite asignar una función a una variable. Se llama función anónima. Y se puede escribir de varias maneras:

```javascript

	const MAYORIA_DE_EDAD = 18

	var esMayorDeEdad =function(persona){   	
		return persona.edad >= MAYORIA_DE_EDAD
	}

```

<br>

Sacha prefiere declararla como _‘const’_ y no como _‘var’_ para definir que es una función y no una variable:

```javascript

	const esMayorDeEdad =function(persona){   	
		return persona.edad >= MAYORIA_DE_EDAD
	}

``` 



La palabra clave _‘function’_ puede reemplazarse por un ‘=>’ después de persona y se convierte en un _arrow function_:


```javascript

	const esMayorDeEdad = (persona) => {   	
		return persona.edad >= MAYORIA_DE_EDAD
	}

```

Se pueden seguir quitando caracteres.
Cuando hay un sólo parámetro se pueden quitar los paréntesis.

```javascript

	const esMayorDeEdad = persona => {   	
		return persona.edad >= MAYORIA_DE_EDAD
	}

```

Si una función sólo retorna un valor se puede quitar el keyword _‘return’_ y las llaves _'{}'_.

```javascript

	const esMayorDeEdad = persona => persona.edad >= MAYORIA_DE_EDAD

```

También se puede desestructurar el parámetro ya que sólo nos interesa la edad. Hay que agregar paréntesis:

```javascript

	const esMayorDeEdad =  ({edad}) => persona >= MAYORIA_DE_EDAD

```

<br>
<br>
<br>

## <a name="clase15"> 15 - Estructuras repetitivas: for ... </a>

El bucle _'for'_, se utiliza para repetir una o más instrucciones un determinado número de veces.

Para escribir un bucle _'for'_ se coloca la palabra _'for'_ seguida de paréntesis y llaves.

Ej. 

	for(){ } 

Dentro de los paréntesis irán las condiciones para ejecutar el bucle, y dentro las llaves irán las instrucciones que se deben repetir.

Las condiciones del _'for'_ son 3 comandos separados por ‘;’.

• El primero es la declaración del contador, desde dónde comienza a contar; ‘let i = 1’ en este caso.
• El segundo es hasta dónde cuenta; ‘i <= 365’ en este caso.
• El tercero es incrementar en 1 la variable contador; ‘i++’.

En este ejemplo la variable i la utilizamos como contador.

```javascript

	for(let i=1; i <= 10; i++) {
		console.log(i)
	}
	// 1
	// 2
	// 3
	// 4
	// 5
	// 6
	// 7
	// 8
	// 9
	// 10

```

En el siguiente ejemplo se imprime el peso de la persona (objeto) al iniciar el año y luego del for (365 días) se imprime el peso de esa misma persona después del año.


```javascript

	var sacha = {
		nombre: 'Sacha',
		apellido: 'Lifszyc',
		edad: 28,
		peso: 75
	}

	console.log(`Al inicio del año ${sacha.nombre} pesa ${sacha.peso}kg`);

	const VARIACION_DE_PESO = 0.2
	const aumentoDePeso = persona => persona.peso += VARIACION_DE_PESO
	const bajaDePeso = persona => persona.peso -= VARIACION_DE_PESO

	for (let i = 1; i <= 365; i++) {
		var random = Math.random();
		if(random < 0.25) {
			aumentoDePeso(sacha)
		} else if (random < 0.50) {
			bajaDePeso(sacha)
		}
	}

	console.log(`Al final del año ${sacha.nombre} pesa ${sacha.peso.toFixed(1)}kg`);


```

<br>
<br>
<br>

## <a name="clase16"> 16 - Estructuras repetitivas: while ... </a>

La estructura repetitiva _'while'_ nos permite repetir un loop hasta que se cumple una condición; hasta que la condición entre paréntesis de como resultado ‘true’.


	while(sacha.peso > META) {
		do next...
	}


A demás aprendimos a usar el keyword ‘debugger’ que se usa cuándo nuestro código falla o no se ejecuta.
Cada vez que el código lea esta palabra detiene su ejecución.

En este caso lo insertamos dentro del while, en la primera línea; después, en la consola, en la pestaña ‘sources’ nos muestra dónde se detiene. 
Con los botones superiores lo vamos haciendo avanzar hasta que muestra el error.


	while(sacha.peso > META) {
		debugger
		if(comeMucho()){

<br>
<br>
<br>

## <a name="clase17"> 17 - Estructuras repetitivas: do-while ... </a>

Otra estructura repetitiva es el _'do-while'_. 
A diferencia de la instrucción _'while'_, un bucle _'do…while'_ se ejecuta una vez antes de que se evalúe la expresión condicional.

El ciclo _'do-while'_ va a ejecutar el o los comandos dentro de las llaves del _‘do’_ al menos una vez hasta que la función declarada dentro de los paréntesis del while se cumpla.
El _“al menos una vez”_ es porque el flujo de ejecución comienza con _‘do’_ (hacer) y luego verifica por primera vez la condición.


```javascript

	var contador = 0 
	const llueve = () => Math.random() < 0.25

	do {
		contador++
	} while(!llueve()) 

	console.log(`Fui a ver si llueve ${contador} veces.`)

```

<br>
<br>
<br>

## <a name="clase18"> 18 - Estructuras repetitivas: switch ... </a>


Switch se utiliza para realizar diferentes acciones basadas en múltiples condiciones.

Prompt, muestra un cuadro de mensaje que le pide al usuario que ingrese algúna información.

Break, sirve para que el browser se salte un bucle.


En este ejemplo le vamos a devolver el horozcopo del día al usuario de acuerdo al signo que ingrese.

```javascript

	while (window) {
		let signo = prompt('Cuál es tu signo?')

		switch (signo) {
			case 'aries':
				alert('Aries empezará un año con...')
				break
			case 'tauro':
				alert('Tanta carga de trabajo que Tauro... ')
				break
			case 'géminis':
			case 'geminis':
				alert('Durante el mes de enero...')
				break
			case 'cáncer':
			case 'cancer':
				alert('La situación económica de Cáncer podría tener...')
				break
			case 'leo':
				alert('A pesar de las prisas por terminar un proyecto...')
				break
			case 'virgo':
				alert('Durante el mes de enero se presentan...')	
				break
			case 'libra':
				alert('La situación económica de Libra... ')	
				break
			case 'escorpio':
				alert('Enero, será un mes en el cual Escorpio deberá...')	
				break
			case 'sagitario':
				alert('Sagitario empezará un poco tenso ... ')	
				break
			case 'capricornio':
				alert('El fuerte carácter de Capricornio...')	
				break
			case 'acuario':	
				alert('Los astros se han alineado estos primeros días... ')	
				break
			case 'piscis':
				alert('Después de tantas distracciones...')	
				break
			default:
				alert('No es un signo válido.')
				break
		}
	}

```



<br>
<br>
<br>
# <a name="sec3"></a>Sección III - Arrays
<br>
<br>

## <a name="clase19"> 19 - Introducción a los arrays</a>

Los arrays son estructuras de datos que nos permiten organizar elementos dentro de una collección. 
Estos elementos pueden ser números, strings, booleanos, objetos, etc.
Luego es posible realizar operaciones sobre esa colección.

Según la documentación de developer.mozilla.org; …‘es un objeto global que es usado en la construcción de arrays, que son objetos tipo lista de alto nivel’.

Para indicar que una variable es un array se usan los corchetes rectos:

	var array = []

Y para mostrar el contenido:


```javascript

	var sacha = {
	    nombre: 'Sacha',
	    apellido: 'Lifszyc',
	    altura: 1.72
	}

	var alan = {
	    nombre: 'Alan',
	    apellido: 'Perez',
	    altura: 1.86
	}

	var martin = {
	    nombre: 'Martin',
	    apellido: 'Gomez',
	    altura: 1.85
	}

	var dario = {
	    nombre: 'Dario',
	    apellido: 'Juarez',
	    altura: 1.71
	}

	var vicky = {
	    nombre: 'Vicky',
	    apellido: 'Zapata',
	    altura: 1.56
	}

	var paula = {
	    nombre: 'Paula',
	    apellido: 'Barros',
	    altura: 1.76
	}

	var personas = [sacha,alan,martin,dario,vicky,paula];

	personas[0]
	//{nombre: "Sacha", apellido: "Lifszyc", altura: 1.72}
	
	personas[1] 	
	{nombre: "Alan", apellido: "Perez", altura: 1.86}
	
	// El 0 y el 1 representan respectivamente el subíndice del elemento que se va a mostrar, el orden en que están cargados en el array.

	personas[0].nombre
	// "Sacha"
	
	personas[3].altura
	//1.71

	//también se puede usar
	personas[0].['nombre']
	// "Sacha"
	
	personas[3].['altura']
	//1.71

```

También se puede recorrer un array con un for loop e ir imprimiendo las propiedades deseadas del mismo:

```javascript
	
	for(var i=0; i<personas.length; i++){
	  var persona=personas[i];
	  console.log(`${persona.nombre} mide ${persona.altura}.`);
	}	

	// Sacha mide 1.72.
	// Alan mide 1.86.
	// Martin mide 1.85.
	// Dario mide 1.71.
	// Vicky mide 1.56.
	// Paula mide 1.76.

```


<br>
<br>
<br>

## <a name="clase20"> 20 - Filtrar un array</a>

Para filtrar necesitamos dos cosas: una función y una condición.
Usamos la función nativa de javascript ‘filter()’ que recibe una condición como parámetro.

En este ejemplo nuestra condición es que la estatura de las personas sea mayor de 1.80mts.

```javascript

	var sacha = {
	    nombre: 'Sacha',
	    apellido: 'Lifszyc',
	    altura: 1.72
	}

	var alan = {
	    nombre: 'Alan',
	    apellido: 'Perez',
	    altura: 1.86
	}

	var martin = {
	    nombre: 'Martin',
	    apellido: 'Gomez',
	    altura: 1.85
	}

	var dario = {
	    nombre: 'Dario',
	    apellido: 'Juarez',
	    altura: 1.71
	}

	var vicky = {
	    nombre: 'Vicky',
	    apellido: 'Zapata',
	    altura: 1.56
	}

	var paula = {
	    nombre: 'Paula',
	    apellido: 'Barros',
	    altura: 1.76
	}

	var personas = [sacha, alan, martin, dario, vicky, paula]
	
	const esAlta = ({ altura }) => altura > 1.8
	var personasAltas = personas.filter(esAlta)

	console.log(personasAltas)
	
	// También puede escribirse así:
	
	var personasAltas = personas.filter(function(){
		return personas.altura > 1.8
	})

```

El método _'filter( )'_ crea una nueva matriz con todos los elementos que pasan la prueba implementada por la función proporcionada.
Recuerda que si no hay elementos que pasen la prueba, _'filter'_ devuelve un array vacío.


<br>
<br>
<br>

## <a name="clase21"> 21 - Transformar un array</a>

El método _map()_ itera sobre los elementos de un array en el orden de inserción y devuelve array nuevo con los elementos modificados.
_map()_ siempre nos devuelve un nuevo array.
En este ejemplo lo usamos para cambiar la unidad de medida de la altura.

```javascript
	
	var personas = [sacha, alan, martin, dario, vicky, paula]

	const pasarAlturaACmts = persona => ({
		...persona,
		altura: persona.altura * 100
	})
	var alturaEnCmts = personas.map(pasarAlturaACmts)
	
```

Otra manera que se mostró en la clase.
Pero esta función modifica también el array ingresado, así que paso a ser la forma correcta la que está en el ejemplo anterior.

```javascript

	const pasarAlturaACmts = persona => {
		persona.altura *= 100// Es lo mismo que persona.altura = persona.altura * 100
		return persona
	}

```


<br>
<br>
<br>

## <a name="clase22"> 22 - Reducir un array a un valor</a>

**Función Reduce**

Es otra de las funciones más usadas con arrays en JS.
Reduce un array a un valor único.

Si lo que queremos es calcular la cantidad total de libros de las personas definidas en los siguientes objetos es posible usar un for e ir incrementando un acumulador. Pero se ajusta mucho más para tal fin el método .reduce()


```javascript

	var sacha = {
	    nombre: 'Sacha',
	    cantidadDeLibros: 111
	}
	var alan = {
	    nombre: 'Alan',
	    cantidadDeLibros: 78
	}
	var martin = {
	    nombre: 'Martin',
	    cantidadDeLibros: 132
	}
	var dario = {
	    nombre: 'Dario',
	    cantidadDeLibros: 90
	}
	var vicky = {
	    nombre: 'Vicky',
	    cantidadDeLibros: 91
	}
	var paula = {
	    nombre: 'Paula',
	    cantidadDeLibros: 182
	}

	var personas = [sacha, alan, martin, dario, vicky, paula]

```

Con un loop _for_...


```javascript

	var acum = 0

	for (var i = 0; i < personas.length; i++) {
		acum = acum + personas[i].cantidadDeLibros
	}

	console.log(`Entotal todos tienen ${acum} libros.`)


```

Con el método .reduce():


```javascript

	const reducer = (acum, persona) => acum + persona.cantidadDeLibros
	var totalDeLibros = personas.reduce(reducer, 0)
	console.log(`Entotal todos tienen ${totalDeLibros} libros.`)

```


<br>
<br>
<br>

# <a name="sec4"> Sección IV - Programación Orientada a Objetos en JavaScript (POO)</a>

<br>
<br>

## <a name="clase23"> 23 - Como funcionan las clases en JavaScript</a>


En JavaScript hablar de _objetos_ es más bien referirse a _**Prototipos**_ y no tanto a _clases_. Si bien en las nuevas versiones de JavaScript existen las _clases_ no son clases como tales, como las pordríamos conocer en cualquier otro lenguaje de programación; no existe la _herencia_ como tal.
Pero sí existen los _**Prototipos**_ y vamos a ver que esas llamadas _clases_ terminan siendo _**Prototipos**_.

**Qué son los _prototipos_:**

> ..."comenzaremos diciendo que (en JavaScript) todos los objetos dependen de un prototipo y que _**los prototipos son objetos**_, es más cualquier objeto puede ser un prototipo"… 
> ..."un prototipo es un objeto del que otros objetos heredan propiedades. Los objetos siempre heredan propiedades de algún objeto anterior, de este modo solo el objeto original y primigenio de javascript es el único que no hereda de nadie…

			**Referencia:** http://mialtoweb.es/prototipos-en-javascript/


**Objetos => Prototipos**

Crear un prototipo es muy similar a crear una variable:

• se antepone el keyword _function_;
• la primer letra del nombre va en mayúscula;
• para invocar un nuevo objeto a partir de este _**prototipo**_ se usa el keyword _'new'_.

```javascript

	function Persona(){
		console.log('Hola, soy un nuevo objeto.')	
	}
	var pablo = new Persona()

```

• se le pueden pasar parámetros;
• para generar nuevos parámetros o atributos dentro de la declaración del objeto se usa el keyword 'this'
• es implícito en javaScript el retornar el objeto que se está creando 


```javascript

	function Persona(nombre, apellido){
		this.nombre = nombre
		this.apellido = apellido
	}
	var pablo = new Persona('Pablo', 'Andrés')

```

• es posible anexar funciones al prototipo usando el apéndice _.prototype_ precedido de el nombre que le asignamos a nuestro nuevo _**prototipo**_ y sucedido del nombre de nuestra nueva función encadenados. Luego este se iguala a una función anónima.

• se pueden usar los mismos atributos que en el objeto (_this.xxx_)


```javascript

	function Persona(nombre, apellido){
		this.nombre = nombre
		this.apellido = apellido
	}

	Persona.prototype.saludar = function(){
		console.log(`Hola me llamo ${this.nombre} ${this.apellido}`)
	}

	var pablo = new Persona('Pablo', 'Andrés')
	var joaquin = new Persona('Joaquín', 'Perez')
	var rosa = new Persona('Rosa', 'Mosqueta')

	rosa.saludar()
	// Hola me llamo Rosa Mosqueta

```

<br>
<br>
<br>

## <a name="clase24"> 24 - Modificando un prototipo</a>

  El prototipo es un objeto de javascript, si lo modificamos en un cierto lugar del código, a una cierta altura, a partir de ahí va a quedar modificado.
  Por lo que una buena práctica, o más bien la manera de declarar un prototipo es al inicio del código y en bloque, es decir todo el código junto (propiedades y funciones del prototipo).
  De otra manera, si queremos correr una función antes de declararla JS arrojará un error y quedará interrumpido el flujo de ejecución.

Ej:

```javascript

	function Persona(nombre, apellido, altura) {
	  this.nombre = nombre
	  this.apellido = apellido
	  this.altura = altura
	}
	Persona.prototype.saludar = () => {
	  console.log(`Hola, me llamo ${this.nombre} ${this.apellido}`)
	}

	Persona.prototype.soyAlto = function() { 
	  return this.altura > 1.8 
	}

	var sacha = new Persona('Sacha', 'Lifszyc', 1.72)
	var erika = new Persona('Erika', 'Luna', 1.65)
	var arturo = new Persona('Arturo', 'Martinez', 1.89)

	sacha.soyAlto()
	// false
	
	erika.soyAlto()
	// false
	
	arturo.soyAlto()
	// true


```
<br>

Si declaro la función al final del código, después de llamar a la función; retorna un error _'Uncaught TypeError: sacha.soyAlto is not a function'_

```javascript

	function Persona(nombre, apellido, altura) {
	  this.nombre = nombre
	  this.apellido = apellido
	  this.altura = altura
	}
	Persona.prototype.saludar = () => {
	  console.log(`Hola, me llamo ${this.nombre} ${this.apellido}`)
	}
	//Persona.prototype.soyAlto = () => this.altura > 1.8
	var sacha = new Persona('Sacha', 'Lifszyc', 1.72)
	var erika = new Persona('Erika', 'Luna', 1.65)
	var arturo = new Persona('Arturo', 'Martinez', 1.89)

	sacha.soyAlto()
	erika.soyAlto()
	arturo.soyAlto()

	Persona.prototype.soyAlto = function() { 
	  return this.altura > 1.8 
	}
	// Uncaught TypeError: sacha.soyAlto is not a function

```
<br>

Si convierto la función en _'arrow function'_ también tendré conflictos pero esta vez con el _'this'_; siempre obtendremos _false_ como respuesta a la función ya que la propiedad _'this.altura'_ es _'undefined'_.


```javascript

	function Persona(nombre, apellido, altura) {
	  this.nombre = nombre
	  this.apellido = apellido
	  this.altura = altura
	}
	Persona.prototype.saludar = () => {
	  console.log(`Hola, me llamo ${this.nombre} ${this.apellido}`)
	}
	Persona.prototype.soyAlto = () => this.altura > 1.8

	var sacha = new Persona('Sacha', 'Lifszyc', 1.72)
	var erika = new Persona('Erika', 'Luna', 1.65)
	var arturo = new Persona('Arturo', 'Martinez', 1.89)

	sacha.soyAlto()
	// false
	
	erika.soyAlto()
	// false
	
	arturo.soyAlto()
	// false

```

<br>
<br>
<br>

## <a name="clase25"> 25 - El contexto de las funciones: Quién es _this_?</a>

Al cambiar una función por un arrow function en el código nos comenzó a arrojar valores ‘undefined’.
La propiedad _'this.altura'_ es _'undefined'_ debido a que _'this'_ no refiere al prototipo que nosotros creamos.

Al debbuguear nos muestra que _this_ === _window_. 

• **_’this’ en el espacio global refiere al objeto 'window'_**; 'this' **es** el objeto 'window', _**el mismo campo en memoria**_.

• Los arrow function refieren siempre al _'this'_ del _'window'_ **y no del prototipo.**


<br>
<br>
<br>

## <a name="clase26"> 26 - La verdad oculta sobre las clases en JavaScript</a>

Cómo hago para que un prototipo herede de otro?

> …“JS no soporta la herencia porque no soporta las clases, no hay clases, hay prototipos a los que les vamos agregando métodos que reciben funciones, saben quien es ‘this’ y saben como ejecutarlas. Pero no existe un sistema como tal donde yo diga: _ "este prototipo va a heredar de otro”…
> Lo que sí existe es la 'herencia prototipal’

Cómo funciona? 
Es posible crear _‘prototipoHijo’_ que van a ser un subtipo del _'prototipoPadre'_ (_persona_ en el ejemplo que venimos usando), podemos crear por ejemplo un sub-tipo de _'persona'_, un ‘desarrollador’.

Este _‘prototiposHijo’_, cada vez que sea requerido buscará los métodos en sí mismo, luego si no los encuentra, buscará en su _'prototipoPadre'_, _'prototipoAbuelo'_ … y así hasta llegar al _'prototipo'_ base de todos los objetos que en JavaScript es _'object'_. 
Si _'object'_ no conoce ese mensaje, recién ahí es que javaScript lanzará el error de que ese método no puede ejecutarse.

Para crear nuestro 'desarrollador'  **generamos este _‘prototipoHijo’_ inmediatamente después del código del _'prototipoPadre'_**, _'Persona'_ en este caso.
Y agregamos un método a este _‘prototiposHijo’_ para que devuelva un saludo particular de desarrollador.

```javascript


	function Desarrollador(nombre, apellido){
		this.nombre = nombre
		this.apellido = apellido
	}
	Desarrollador.prototype.saludar = function(){
		console.log(`Hola, me llamo ${this.nombre}${this.apellido} y soy desarrollader.`)
	}


```
<br>

**Pero cómo hacemos para que este _‘prototipoHijo’_ herede los métodos del _'prototipoPadre'_?**

Para esto tenemos que generar una nueva función que le diga al _‘prototipoHijo’_ quién va a ser su _'prototipoPadre'_ y la llamamos inmediatamente después de la declaración del _‘prototipoHijo’_ y antes de declarar las funciones de este mismo, ya que si queremos "pisar" algún método del _'prototipoPadre'_, esta llamada va a volver a sentenciar los métodos del _'prototipoPadre'_.


_(Hasta las regulaciones del ECMAScript esta era la única manera de generar herencia en JS)_


```javascript

	// función enlace
	function heredaDe(prototipoHijo, prototipoPadre) {
	  ...
	}

	// función padre
	function Persona(nombre, apellido, altura) {
	  ...
	}
	Persona.prototype.saludar = function () {
	  ...
	}
	Persona.prototype.soyAlto = function () {
	  ...
	}

	// función hijo
	function Desarrollador(nombre, apellido) {
	  this.nombre = nombre
	  this.apellido = apellido
	}
	
	// invocación de función enlace 
	heredaDe(Desarrollador, Persona)

	//método de función hijo
	Desarrollador.prototype.saludar = function () {
	  console.log(`Hola, me llamo ${this.nombre} ${this.apellido} y soy desarrollador/a`)
	}

```

La funcionalidad de la función que va a generar el enlace de herencia es la siguiente.

• Primero generamos una variable a la que le cargamos una función vacía:

	function heredaDe(prototipoHijo, prototipoPadre) {
	    var fn = function () {}
	}

• Luego asignamos el prototipo del _'prototipoPadre'_ a esta misma:
	
	function heredaDe(prototipoHijo, prototipoPadre) {
	    var fn = function () {}
	    fn.prototype = prototipoPadre.prototype
	}

• Y entonces ahora asignamos el _'prototipoPadre'_ al prototipo del _‘prototipoHijo’_. Lo hacemos de esta manera así, al estar generando un clon del _'prototipoPadre'_ no "pisamos" o modificamos nada en este.


	function heredaDe(prototipoHijo, prototipoPadre) {
	    var fn = function () {}
	    fn.prototype = prototipoPadre.prototype
	    prototipoHijo.prototype = new fn
	}


• Y finalmente llamamos al _'constructor'_ del mismo _‘prototipoHijo’_ para que se refiera a sí mismo y no al constructor del _'prototipoPadre'_


	function heredaDe(prototipoHijo, prototipoPadre) {
	  var fn = function () {}
	  fn.prototype = prototipoPadre.prototype
	  prototipoHijo.prototype = new fn
	  prototipoHijo.prototype.constructor = prototipoHijo
	}

Este es un método muy complejo, ya obsoleto. Hoy por hoy lo hacemos de otra manera.

El código completo queda así:

```javascript

	function heredaDe(prototipoHijo, prototipoPadre) {
	  var fn = function () {}
	  fn.prototype = prototipoPadre.prototype
	  prototipoHijo.prototype = new fn
	  prototipoHijo.prototype.constructor = prototipoHijo
	}

	function Persona(nombre, apellido, altura) {
	  this.nombre = nombre
	  this.apellido = apellido
	  this.altura = altura
	}

	Persona.prototype.saludar = function () {
	  console.log(`Hola, me llamo ${this.nombre} ${this.apellido}`)
	}

	Persona.prototype.soyAlto = function () {
	  return this.altura > 1.8
	}

	function Desarrollador(nombre, apellido) {
	  this.nombre = nombre
	  this.apellido = apellido
	}

	heredaDe(Desarrollador, Persona)

	Desarrollador.prototype.saludar = function () {
	  console.log(`Hola, me llamo ${this.nombre} ${this.apellido} y soy desarrollador/a`)
	}


```

Creamos unos objetos y analizamos como se comportan:


```javascript


	var sacha = new Persona('Sacha', 'Lifszyc', 1.72)
	var erika = new Persona('Erika', 'Luna', 1.65)
	var arturo = new Desarrollador('Arturo', 'Martinez', 1.89)

	sacha.saludar()
	// Hola, me llamo Sacha Lifszyc
	
	erika.saludar()
	// Hola, me llamo Erika Luna
	
	arturo.saludar()
	// Hola me llamo Arturo Martinez y soy desarrollador/a.
	// este nos arroja el saludo de _Desarrollador_ ya que es una instancia del mismo

```

Ahora analicemos al atributo _.prototipe_ en consola:


```javascript

	Persona.prototype
	// {saludar: ƒ, soyAlto: ƒ, constructor: ƒ}
	//	saludar: ƒ ()
	//	soyAlto: ƒ ()
	//	constructor: ƒ Persona(nombre, apellido, altura)
	//	__proto__: Object

```

Vemos que _.prototype_ es un atributo que tiene todas las funciones de Persona. 
Es un **objeto** que tiene métodos y su propio _constructor_ a demás de un atributo __proto__ que es el que hace referencia al _'prototipoPadre'_; en este caso _'Object'_

	__proto__: Object

Veamos a quién hace referencia el _‘prototipoHijo’_


```javascript

	Desarrollador.prototype
	//Persona {constructor: ƒ, saludar: ƒ}
	//	constructor: ƒ Desarrollador(nombre, apellido)
	//	saludar: ƒ ()
	//	__proto__:
	//		saludar: ƒ ()
	//		soyAlto: ƒ ()
	//		constructor: ƒ Persona(nombre, apellido, altura)
	//		__proto__: Object

```

  Y aquí vemos que hace referencia al prototipo _Persona_ aunque en principio nos muestra su propio _'constructor'_ y su propio método _'saludar'_. Dentro del _'proto'_ nos muestra los métodos del _'prototipoPadre'_ y a su vez el _'proto'_ de este hace referencia a su _'prototipoPadre'_ que es nuevamente _'Object'_
  Es desde este encadenamiento que es posible que hagamos la invocación de los métodos del _'prototipoPadre'_ en el _‘prototipoHijo’_.
  


<br>
<br>
<br>

## <a name="clase27"> 27 - Clases en JavaScript</a>

Como ya se mencionó en esta referencia, a partir del standar de código de JavaScript, ECMAScript 2015 y sus subsiguientes versiones se modificó la forma vista de generar herencia prototipal.
Estos standars no agregaron funcionalidad nueva a este tema pero sí lo ha facilitado y sintetizado mucho.

> Dato extra: "**_sugar syntax_**; este es un término usado para describir una característica en un lenguaje que te permite hacer algo más facilmente con menos escritura o código, pero en realidad no agrega ninguna funcionalidad nueva al lenguaje".

Definimos la variable persona de acuerdo a ECMA-Script 2015 entonces:


```javascript


	class Persona {
		constructor(nombre, apellido, altura, genero){
			this.nombre = nombre
			this.apellido = apellido
			this.altura = altura
			this.genero = genero
		}
		saludar(){
			console.log(`Hola me llamo ${this.nombre}${this.apellido}`)
		}
		soyAltX(){
			var altX = this.genero == 'masculino' ? 'alto' : 'alta'
			var string = this.altura >= 1.8 	? `Soy ${this.nombre}${this.apellido} y definitivamente soy ${altX}.` 
							: `Soy ${this.nombre}${this.apellido} y no, no soy ${altX}.`
			console.log(string)
		}
	}



```

Vemos que se utiliza el keyword _class_ para definir el prototipo (aunque se llame 'class' sigue siendo un prototipo). Y que agregamos una definición de _constructor_ como la función que recibe los parámetros.
También podemos, a continuación de este y dentro del contexto de la clase y no por fuera definir los métodos que esta _clase_ va a utilizar.

<br>

Cómo logramos que una clase herede de otra?

Simplemente definimos una nueva clase y agregamos a esta el keyword _extends_ seguido de la clase de la que va a Heredar. A demás, en el constructor de la misma debemos invocar los parámetros de la función de la que hereda con el keyword _super_.


```javascript

	class Desarrollador extends Persona{
		constructor(nombre, apellido, altura, genero){
			super(nombre, apellido, altura, genero) // super llama los atributos del padre
		}
		saludar(){
			console.log(`Hola, me llamo ${this.nombre} ${this.apellido} y soy desarrollader.`)
		}
	}


```
Notemos que _Persona.prototype_ en consola seguirá arrojando el objeto _prototype_ exactamente igual que con la sintaxis referida exclusivamente a _prototype_.



<br>
<br>
<br>

# <a name="sec5">Sección V - Asincronismo</a>

<br>
<br>

## <a name="clase28"></a> 28 - Funciones como parámetros

Antes de comenzar a hablar de asincronismo tenemos que comprender la mecánica de las funciones como parámetro.
Es posible pasar funciones como parámetro, como si fuera cualquier otro tipo de variable.

Cómo se declara?
Como cualquier función.

La siguiente función es una respuesta a la función saludar del código que traemos de las clases anteriores:

	functionresponderSaludo(){
		console.log(`Buen día`)
	}

Cómo se implementa al prototipo?
Se agrega un parámetro a la función que la va a disparar dentro del prototipo ( ‘saludar(fn)’, en este caso ) y un if que evalúe si es llamada.

```javascript

	saludar(fn){
	    console.log(`Hola me llamo ${this.nombre} ${this.apellido}`)
	    if(fn){
	        fn()
	    }
	}

```
Cómo se ejecuta?	
Se ejecuta invocando la función sin paréntesis dentro de los paréntesis de la función saludar ya que es una respuesta al saludo:

	sacha.saludar(responderSaludo)

Si quiero pasar parámetros?

Los agrego al declarar la función y luego los agrego entre paréntesis a la invocación de la misma dentro de la función que la dispara en el prototipo. Funcionan implícitamente, es decir, no se agregan cuando invoco la función dentro del ‘saludar()’.

En la declaración:


```javascript


	functionresponderSaludo(_nombre_, _apellido_, _esDev_){
		console.log(`Buen día ${_nombre_}${_apellido_}.`)
		if (_esDev_) {
			console.log(`Ah mirá, no sabía que eras dev.`)
		}
	}

```

En la función nativa:

```javascript

	saludar(fn){
		console.log(`Hola me llamo ${this.nombre} ${this.apellido}`)
		if(fn){
			fn(_this.nombre_, _this.apellido_)
		}
	}

```

Se invoca:

```javascript

	sacha.saludar(responderSaludo)

```

Para despejar la lectura del código y escribir menos:


```javascript

	saludar(fn){
		console.log(`Hola me llamo ${this.nombre}${this.apellido}`)
		if(fn){
			var {nombre, apellido} = this 
			// == var nombre = this.nombre // var apellido = this.apellido
			fn(nombre, apellido)
		}
	}


```
<br>

Hay valores que al ser evaluados dentro de un if dan verdadero y otros falso, en este caso fn dentro del if evalúa si existe la función en la invocación de saludar().

El código completo quedaría así:

```javascript

	classPersona{
		constructor(nombre, apellido, altura, genero){
			this.nombre = nombre
			this.apellido = apellido
			this.altura = altura
			this.genero = genero
		}
		saludar(fn){
			console.log(`Hola me llamo ${this.nombre}${this.apellido}`)
			if(fn){
				var {nombre, apellido} = this
				fn(nombre, apellido)
			}
		}
		soyAltX(){
			var altX = this.genero == 'masculino' ? 'alto' : 'alta'
			var string = this.altura >= 1.8 ? `Soy ${this.nombre}${this.apellido} y definitivamente soy ${altX}.` 
											: `Soy ${this.nombre}${this.apellido} y no, no soy ${altX}.`
			console.log(string)
		}
	}

	classDesarrolladorextendsPersona{
		constructor(nombre, apellido, altura){
			super(nombre, apellido, altura)
		}
		saludar(fn){
			console.log(`Hola, me llamo ${this.nombre}${this.apellido} y soy desarrollader.`)
			if(fn){
				var {nombre, apellido} = this
				fn(nombre, apellido, true)
			}
		}
	}

	functionresponderSaludo(nombre, apellido, esDev){
		console.log(`Buen día ${nombre}${apellido}.`)
		if (esDev) {
			console.log(`Ah mirá, no sabía que eras dev.`)
		}
	}

	var pablo = new Persona('Pablo', 'Andrés', 1.78, 'masculino')
	var joaquin = new Desarrollador('Joaquín', 'Perez', 1.91, 'masculino')
	var rosa = new Persona('Rosa', 'Mosqueta', 1.81, 'femenino')
	var elis = new Persona('Elis', 'Detta', 1.73, 'femenino')

	pablo.saludar()
	joaquin.saludar(responderSaludo)
	rosa.saludar(responderSaludo)
	elis.saludar(responderSaludo)


```


<br>
<br>
<br>

## <a name="clase29"></a> 29 - Cómo funciona el asincronismo en JavaScript

<br>
<br>
<br>

## <a name="clase30"></a> 30 - Cómo funciona el tiempo en JavaScript

<br>
<br>
<br>

## <a name="clase31"></a> 31 - Callbacks

<br>
<br>
<br>

## <a name="clase32"></a> 32 - Haciendo múltiples requests

<br>
<br>
<br>

## <a name="clase33"></a> 33 - Manejando el Orden y el Asincronismo en JavaScript


<br>
<br>
<br>

## <a name="clase34"></a> 34 - Manejo de errores con callbacks


<br>
<br>
<br>

## <a name="clase35"></a> 35 - Promesas


<br>
<br>
<br>

## <a name="clase36"></a> 36 - Promesas Encadenadas


<br>
<br>
<br>

## <a name="clase37"></a> 37 - Múltiples promesas en paralelo

<br>
<br>
<br>

## <a name="clase38"></a> 38 - Async-await: lo último en asincronismo




<br>
<br>
<br>

## <a name="clase39"></a> 39 - 

