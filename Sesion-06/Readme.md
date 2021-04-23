
[`Programación con JavaScript`](../Readme.md) > `Sesión 06`

# Sesión 6: Programación funcional

## Objetivos

Crear constructores a partir de los cuales se puedan instanciar múltiples objetos.

---

## Tabla de Contenidos

- **[Programación funcional](#programación-funcional)**

- **[Inmutabilidad](#inmutabilidad)**

	- [Ejemplo 1: Mutando objetos](./Ejemplo-01)

- **[Funciones puras](#funciones-puras)**

	- [Ejemplo 2: Creando funciones puras](./Ejemplo-02)

- **[Funciones de primera clase](#funciones-de-primera-clase)**

- **[Funciones de alto orden](#funciones-de-alto-orden)**

	- [Ejemplo 3: Sumando Dígitos](./Ejemplo-03)

	- [Reto 1: Flatten](./Reto-01)

	- [Reto 2: Compact](./Reto-02)

	- [Reto 3: Loop](./Reto-03)

---

## Programación funcional

Como vimos en la sesión anterior existen distintos paradigmas de programación. La programación funcional es un paradigma declarativo, es decir, se enfoca en el _qué_ se desea lograr sin preocuparse mucho en el _cómo_ (el lenguaje de programación se encarga de esta parte).

```javascript
var numbers = [1, 2, 3, 4, 5];
var doubles = [];

for(var i = 0; i < numbers.length; i++) {
	doubles.push(numbers[i] * 2);
}

console.log(numbers); // [1, 2, 3, 4, 5]
console.log(doubles); // [2, 4, 6, 8, 10]
```

Este es un ejemplo de código imperativo. Generalmente usar ciclos es programación imperativa pues queda del lado del programador controlar cuándo iniciar, cuándo terminar y qué hacer en cada ciclo.

```javascript
var numbers = [1, 2, 3, 4, 5];
var doubles = numbers.map(function(number) {
	return number * 2;
});

console.log(numbers); // [1, 2, 3, 4, 5]
console.log(doubles); // [2, 4, 6, 8, 10]
```

Esta es la forma declarativa del mismo código. Ambos fragmentos de código hacen exactamente lo mismo, crear un arreglo `doubles` con el doble de cada elemento del arreglo `numbers`. La diferencia con el segundo ejemplo es que hacemos uso del método `map()`, el programador no se encarga de controlar cuándo y dónde terminar el ciclo, sólo se encarga del resultado, obtener el doble de cada elemento dentro de `numbers`.

> El método map() crea un nuevo array con los resultados de la llamada a la función indicada aplicados a cada uno de sus elementos.

---

## Inmutabilidad

Decimos que algo es mutable cuando puede ser cambiado o modificado. Por lo tanto, inmutable es algo que no puede ser alterado. En términos de programación, las variables inmutables nunca cambian su valor. Este es un principio muy importante en la programación funcional, de hecho, lenguajes de programación como Elixir o Erlang no permiten la mutación de variables.

En lugar de alterar una variable, creamos nuevos valores y reemplazamos los antiguos. Si bien JavaScript no es puramente funcional, es lo suficientemente flexible como para permitir o pretender serlo.

Para llevar este concepto a la práctica es importante siempre preferir crear una nueva variable en lugar de intentar modificar la original. Esto se puede llevar a cabo con métodos como `map()` que no altera el arreglo original, o bien creando tus propias funciones inmutables.

#### [Ejemplo 1: Mutando objetos](./Ejemplo-01)

---

## Funciones puras

Para que una función pueda ser considerada pura debe cumplir dos reglas:

1. El valor retornado siempre es el mismo cuando se da el mismo valor de entrada.

2. No debe producir side effects (efectos secundarios).

![Pure Function](./assets/pure-function.png)

El primer punto se refiere a que si ejecutamos la misma función varias veces con los mismos argumentos siempre obtendremos el mismo resultado.

```javascript
function add(a, b) {
	return a + b;
}
```

Podemos llamar las veces que queramos la esta función de la forma `add(1, 2)` y sabemos que siempre vamos a obtener el mismo resultado `3`.

```javascript
function randomNumber() {
	return Math.floor(Math.random() * 10);
}
```

Esta función no cumple la primera regla porque si la llamamos 10 veces, obtendremos cada vez un número aleatorio entre 1 y 10. No podemos predecir el valor de retorno de esta función.

Los side effects son un término más amplio que el anterior. A grandes rasgos significa modificar algo fuera de la función. Algunos ejemplos:

1. Mutar los parámetros que recibe una función como en el [Ejemplo 1](./Ejemplo-01).

2. Modificar cualquier variable fuera de la función.

3. Llamadas a una API.

4. `console.log()`

La función anterior `add()` también cumple con la segunda regla, no produce side effects. Sólamente está trabajando con las variables que recibe la función y siempre retorna un valor.

#### [Ejemplo 2: Creando funciones puras](./Ejemplo-02)

---

## Funciones de primera clase

En un lenguaje de programación se dice que una función es de primera clase cuando puede ser tratada como cualquier otra variable. Por ejemplo, cuando puede ser pasada como argumento a otras funciones o cuando puede ser asignada a una variable. Este comportamiento no es explusivo de JavaScript, otros lenguajes de programación como R o Scala también cuentan con esta característica.

Ya hemos guardado funciones anónimas en una variable anteriormente.

```javascript
var square = function(number) {
	return number * number;
}

var squareOfFour = square(4);

console.log(squareOfFour); // 16
```

Por lo tanto, las expresiones de funciones como estas son consideradas funciones de primera clase.

---

## Funciones de alto orden

Cuando una función recibe otra función como parámetro se le llama de alto orden o de orden superior. JavaScript nos proporciona varias funciones de alto orden para trabajar con estructuras de datos. Las más usadas son `map()`, `filter()` y `reduce()`.

Al principio de la sesión vimos cómo funciona `map()`, aplica una función sobre cada elemento del arreglo. Es importante destacar que no muta el arreglo original.

```javascript
var numbers = [1, 2, 3, 4, 5];
var doubles = numbers.map(function(number) {
	return number * 2;
});

console.log(numbers); // [1, 2, 3, 4, 5]
console.log(doubles); // [2, 4, 6, 8, 10]
```

De igual forma `filter()` crea un nuevo arreglo pero sólo con aquellos elementos que retornen true por la función que actúa como predicado.

```JavaScript
var numbers = [1, 2, 3, 4, 5];

var evenNumbers = numbers.filter(function(number) {
	return number % 2 === 0;
});

console.log(evenNumbers); // [2, 4]
```

Por último, `reduce()` acumula o reduce todos los elementos a un valor único según la función dada.

```JavaScript
var numbers = [1, 2, 3, 4, 5];

var sum = numbers.reduce(function(accumulator, currentValue) {
	return accumulator + currentValue;
}, 0); // Initial value

console.log(sum); // 15
```

#### [Ejemplo 3: Sumando Dígitos](./Ejemplo-03)

#### [Reto 1: Flatten](./Reto-01)

#### [Reto 2: Compact](./Reto-02)

#### [Reto 3: Loop](./Reto-03)
