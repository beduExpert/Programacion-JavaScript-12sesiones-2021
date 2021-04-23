
[`Programación con JavaScript`](../Readme.md) > `Sesión 03`

# Sesión 3: Funciones

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

	- [Reto 2: Número mayor](./Reto-02)

	- [Reto 3: Fibonacci](./Reto-03)

---

## ¿Qué es una función?

Uno de los conceptos más importantes en JavaScript. Una función es un conjunto de sentencias que realizan una tarea o calculan un valor. En lugar de repetir el mismo código una y otra vez, podemos crear una función la cual se puede llamar las veces que sea necesario.

```javascript
function myFunction(parameter1, parameter2) {
	// Código a ejecutar
}
```

- `function` - La palabra clave que usamos para definir una función.

- `myFunction` - Es el nombre que le damos a la función. Puede contener letras, números, guión bajo y el signo de dólar.

- `(parameter1, parameter2)` - Dentro de los paréntesis colocamos los parámetros de la función separados por coma. Los parámetros son variables que se van a usar dentro de la función y no es necesario declararlas nuevamente dentro de la función. Algunas funciones no reciben parámetros, por lo que los paréntesis pueden ir vacios.

#### [Ejemplo 1: Funciones](./Ejemplo-01)

#### [Reto 1: Potenciación](./Reto-01)

---

## Expresiones de función

La sintaxis que hemos visto hasta ahora se le conoce como **declaración de función** o **sentencia de función**. Las funciones también pueden ser creadas mediante una **expresión de función**.

#### [Ejemplo 2: Expresión de función](./Ejemplo-02)

Como vimos en el ejemplo anterior, las funciones son anónimas, es decir no tienen nombre.

```javascript
var square = function(number) {
	return number * number;
}

var squareOfFour = square(4);

console.log(squareOfFour); // 16
```

Pero las expresiones de funciones también pueden tener un nombre para referirse a sí mismas, como en una función recursiva.

```javascript
var factorial = function fac(number) {
	return number < 2 ? 1 : number * fac(number - 1)
}

console.log(factorial(5)); // 120
```

---

## Expresión de función ejecutada inmediatamente

Las expresiones de funciones ejecutadas inmediatamente o **IIFE** por sus siglas en inglés (Immediately Invoked Function Expression) son funciones que se ejecutan inmediatamente después de definirlas. Son útiles cuando queremos ejecutar una función una sola vez y no queremos que otras partes del programa puedan ejecutar dicha función accidentalmente.

#### [Ejemplo 3: IIFE](./Ejemplo-03)

Es común ver este patrón en frameworks o librerías de JavaScript. Al envolver el código en un IIFE están aislando las variables del resto del código y se aseguran que se ejecuta sin necesidad de que el usuario lo tenga que hacer.

#### [Reto 2: Número mayor](./Reto-02)

#### [Reto 3: Fibonacci](./Reto-03)
