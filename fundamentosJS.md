# Índice

### [Clase 4 - Variables](#clase4)
### [Clase 5 - Variables - Strings](#clase5)
    

# Resumen clase por clase:


## <a name="clase4"> Clase 4: Variables </a>


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
  


## <a name="clase5"> Clase 5: Variables - Strings </a>

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
























