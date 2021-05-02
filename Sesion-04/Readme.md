
[`Programación con JavaScript`](../Readme.md) > `Sesión 04`

# Sesión 4: Funciones

## Objetivos

Dividir el trabajo que realiza un programa mediante tareas más pequeñas aisladas del flujo principal.

---

## Tabla de Contenidos

- **[¿Qué es una función?](#qué-es-una-función)**

	- [Ejemplo 1: Funciones](./Ejemplo-01)

	- [Reto 1: Potenciación](./Reto-01)

- **[Expresiones de función](#expresiones-de-función)**

	- [Ejemplo 2: Expresión de función](./Ejemplo-02)

- **[Expresión de función ejecutada inmediatamente](#expresión-de-función-ejecutada-inmediatamente)**

	- [Ejemplo 3: IIFE](./Ejemplo-03)

- **[Arrow functions](#arrow-functions)**
	
	- [Sintaxis](#sintaxis)
		
	- [Paréntesis](#paréntesis)
	
	- [Return Implícito](#return-implícito)

	- [Reto 2: Número mayor](./Reto-02)

	- [Reto 3: Fibonacci](./Reto-03)

---

## ¿Qué es una función?

Uno de los conceptos más importantes en JavaScript. Una función es un conjunto de sentencias que realizan una tarea o
calculan un valor. En lugar de repetir el mismo código una y otra vez, podemos crear una función la cual se puede llamar
las veces que sea necesario.

```javascript
function myFunction(parameter1, parameter2) {
  // Código a ejecutar
}
```

- `function` - La palabra clave que usamos para definir una función.

- `myFunction` - Es el nombre que le damos a la función. Puede contener letras, números, guion bajo y el signo de dólar.

- `(parameter1, parameter2)` - Dentro de los paréntesis colocamos los parámetros de la función separados por coma. Los
	parámetros son variables que se van a usar dentro de la función y no es necesario declararlas nuevamente dentro de la
	función. Algunas funciones no reciben parámetros, por lo que los paréntesis pueden ir vacíos.

#### [Ejemplo 1: Funciones](./Ejemplo-01)

#### [Reto 1: Potenciación](./Reto-01)

---

## Expresiones de función

La sintaxis que hemos visto hasta ahora se le conoce como **declaración de función** o **sentencia de función**. Las
funciones también pueden ser creadas mediante una **expresión de función**.

#### [Ejemplo 2: Expresión de función](./Ejemplo-02)

Como vimos en el ejemplo anterior, las funciones son anónimas, es decir no tienen nombre.

```javascript
const square = function(number) {
  return number * number;
}

const squareOfFour = square(4);

console.log(squareOfFour); // 16
```

Pero las expresiones de funciones también pueden tener un nombre para referirse a sí mismas, como en una función
recursiva.

```javascript
const factorial = function fac(num) {
  return num < 2 ? 1 : num * fac(num - 1)
}

console.log(factorial(5)); // 120
```

---

## Expresión de función ejecutada inmediatamente

Las expresiones de funciones ejecutadas inmediatamente o **IIFE** por sus siglas en inglés (Immediately Invoked Function
Expression) son funciones que se ejecutan inmediatamente después de definirlas. Son útiles cuando queremos ejecutar una
función una sola vez y no queremos que otras partes del programa puedan ejecutar dicha función accidentalmente.

#### [Ejemplo 3: IIFE](./Ejemplo-03)

Es común ver este patrón en frameworks o librerías de JavaScript. Al envolver el código en un IIFE están aislando las
variables del resto del código y se aseguran que se ejecuta sin necesidad de que el usuario lo tenga que hacer.

---

## Arrow functions

Este tipo de funciones presenta una sintaxis más concisa comparada con las funciones normales. Antes de ver la sintaxis
veamos un ejemplo más con funciones normales.

Tenemos un arreglo `firstNames`.

```javascript
const firstNames = [ 'John', 'Jane', 'Mark'];
```

A cada nombre le vamos a agregar el apellido `Doe` y crear un nuevo arreglo `fullNames`. Para esto usaremos un ciclo y
aprovecharemos la flexibilidad de template strings.

```javascript
const firstNames = [ 'John', 'Jane', 'Mark'];

function getFullNames(names) {
  const fullNames = []
	
  for(const name of names) {
    fullNames.push(`${name} Doe`)
  }
  
  return fullNames
}

const fullNames = getFullNames(firstNames)

console.log(fullNames); // ["John Doe", "Jane Doe", "Mark Doe"]
```

Ahora veamos cómo podemos sobreescribir esta función para usar arrow functions.

### Sintaxis

Lo primero que debemos tomar en cuenta es que las arrow functions son funciones anónimas. Significa que el primer paso
es usar una expresión de función.

```javascript
const firstNames = [ 'John', 'Jane', 'Mark'];

const getFullNames = function(names) {
  const fullNames = []
	
  for(const name of names) {
    fullNames.push(`${name} Doe`)
  }
  
  return fullNames
}

const fullNames = getFullNames(firstNames)

console.log(fullNames); // ["John Doe", "Jane Doe", "Mark Doe"]
```

Ahora bien, para escribir un arrow function solo debemos quitar el keyword `function` y agregar lo que se conoce como _
fat arrow_ (`=>`) justo después de los paréntesis que contienen los parámetros de la función.

```javascript
const firstNames = [ 'John', 'Jane', 'Mark'];

const getFullNames = (names) => {
  const fullNames = []
	
  for(const name of names) {
    fullNames.push(`${name} Doe`)
  }
  
  return fullNames
}

const fullNames = getFullNames(firstNames)

console.log(fullNames); // ["John Doe", "Jane Doe", "Mark Doe"]
```

### Paréntesis

Adicionalmente, cuando contamos con un único parámetro los paréntesis pueden ser eliminados.

```javascript
const firstNames = [ 'John', 'Jane', 'Mark'];

const getFullNames = names => {
  const fullNames = []
	
  for(const name of names) {
    fullNames.push(`${name} Doe`)
  }
  
  return fullNames
}

const fullNames = getFullNames(firstNames)

console.log(fullNames); // ["John Doe", "Jane Doe", "Mark Doe"]
```

Eliminar los paréntesis es opcional. Algunos [Style Guides](https://github.com/airbnb/javascript#arrows--one-arg-parens)
sugieren no hacerlo por claridad y consistencia en el código.

### Return implícito

Cuando escribimos `return` estamos definiendo explícitamente lo que debe retornar la función. Muchas veces las funciones
solo retornan un valor sin hacer alguna otra operación antes. Cuando este es el caso podemos omitir el `return` pues el
arrow function asume que se va a retornar lo que sigue después del fat arrow.

```javascript
const logName = (name) => console.log(`Hello ${name}!`);

logName('John Doe'); // Hello John Doe!
```

De esta manera podemos eliminar las llaves, ya que estas definen un bloque de líneas, y eliminar también el
keyword `return`

#### [Reto 2: Número mayor](./Reto-02)

#### [Reto 3: Fibonacci](./Reto-03)
