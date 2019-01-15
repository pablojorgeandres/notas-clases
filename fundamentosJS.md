# Índice

    ### [Clase 4 - Variables](#clase4)
    ### [Clase 5 - Variables - Strings](#clase5)
    

# Resumen clase por clase:


## <a name="clse4"> Clase 4: Variables </a>


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
  


## <a name="clse5"> Clase 5: Variables - Strings </a>
