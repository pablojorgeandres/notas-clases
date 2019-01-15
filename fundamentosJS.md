# Índice

### [Clase 4 - Variables](#clase4)
### [Clase 5 - Variables - Strings](#clase5)
    

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















