[`Programación con JavaScript`](../Readme.md) > `Sesión 02`

---

# Sesión 2: Controles de flujo

## Objetivos

Distinguir las distintas estructuras que permiten controlar el flujo de ejecución de un programa o aplicación

---

## Tabla de Contenidos

- **[Condicionales](#condicionales)**

	- [Operadores lógicos](#operadores-lógicos)

	- [`if`/`else`](#if--else)

		- [Ejemplo 1: Primeras condicionales](./Ejemplo-01)

		- [Reto 1: Controles de flujo](./Reto-01)

	- [`switch`](#switch)

		- [Ejemplo 2: Usando `switch`](./Ejemplo-02)

- **[Operador Ternario](#operador-ternario)**

- **[Truthy y Falsy](#truthy-y-falsy)**

- **[Bucles](#bucles)**

	- [Ejemplo 3: Ciclo `for`](./Ejemplo-03)

	- [Reto 2: Números pares](./Reto-02)

	- [Reto 3: Números primos](./Reto-03)

---

## Condicionales

Las condicionales nos permiten cotrolar el flujo de un programa, es decir, podemos controlar las partes del código que se ejecutarán dependiendo de si una condición se cumple o no.

### Operadores lógicos

JavaScript nos proporciona varios operadores lógicos para que podamos realizar operaciones de comparación.

| Operador | Descripción                                                                                                       | Ejemplos                                                      |
|----------|-------------------------------------------------------------------------------------------------------------------|---------------------------------------------------------------|
| ==       | **Igualdad:** Devuelve `true` si ambos operandos son iguales                                                      | 3 == 3<br> 3 == "3"<br> "mike" == "mike"<br> var1 == true<br> |
| !=       | **Desigualdad:** Devuelve `true` si ambos operandos no son iguales                                                | 3 != 4                                                        |
| ===      | **Estrictamente iguales:**<br> Devuelve `true` si los operandos son igual<br> y tienen el mismo tipo.             | 3 === 3 <br><br> 3 === "3"<br> (Devuelve falso)               |
| !==      | **Estrictamente desiguales:** <br> Devuelve `true` si los operandos no son iguales<br> y/o no son del mismo tipo. | 3 !== "3"                                                     |
| >        | **Mayor que:** Devuelve `true` si el operando de la izquierda<br> es mayor que el operando de la derecha.         | 4 > 3                                                         |
| >=       | **Mayor o igual que:**                                                                                            | 4 >= 4                                                        |
| <        | **Menor que:** Devuelve `true` si el operando de la izquierda<br>  es menor que el operando de la derecha.        | 12 < 15                                                       |
| <=       | **Menor o igual que:**                                                                                            | 15 <= 15                                                      |
| &&       | **And:** Devuelve `true` si ambas condiciones se cumplen                                                          | 2 > 1 && 1 > 0                                                |
| \|\|       | **Or:** Devuelve `true` si una de las condiciones se cumplen                                                      | 2 > 1 \|\| 1 < 0                                                |

### `if` / `else`

El tipo de condición más común de todos. Traducida literalmente del inglés, se la podría llamar la estructura *si...si no*, es decir, *si se cumple la condición, haz esto, y sino, haz esto otro*.

La sintaxis se compone de la siguiente forma:

```javascript
if ( /* Condición a evaluar */ ) {
	/* Código a ejecutar si la condición retorna true */
} else {
	/* Código a ejecutar si la condición retorna false */
}
```

- `if` - La palabra clave que indica que se va a realizar una condicional.
- `( ... )` - Dentro de los paréntesis se coloca la condición a evaluar, la cuál retorna un booleano, es decir, `true` o `false`.
- `{ ... }` - Dentro de las llaves va el texto a ejecutar en caso de que la condición sea `true`.
- `else` - Se utiliza para controlar el flujo en caso de que la condición sea `false`. Si se usa `else`, el código dentro de las llaves que le siguen se ejecuta sólo cuando la condición anterior no se cumplió.

#### [Ejemplo 1: Primeras condicionales](./Ejemplo-01)

#### [Reto 1: Controles de flujo](./Reto-01)

### `switch`

Esta condicional nos permite ejecutar un sólo bloque de código de varios. Es una buena alternativa cuando tenemos múltiples condicionales `if`/`else`.

```javascript
switch ( /* Expresión a evaluar*/ ) {
	case a:
		/* Código a ejecutar */
		break;
	case b:
		/* Código a ejecutar */
		break;
	default:
		/* Código a ejecutar por default */
}
```

- `switch` - La palabra clave que indica que se va a realizar una condicional.
- `( ... )` - Expresión a evaluar.
- `case` - Expresa uno de los posibles valores como resultado de la evaluación que se está haciendo.
- `break` - Detiene la ejecución del bloque y sale del `switch`.
- `default` - Define qué se debe hacer cuando ninguno de los casos se cumple.

#### [Ejemplo 2: Usando `switch`](./Ejemplo-02)

---

## Operador Ternario

El operador ternario es el único operador en JavaScript que consta de tres operandos. Es una buena alternativa para una condición `if`/`else`, ya que presenta una sintaxis más sencilla.

```javascript
condición ? expresión_true : expresión_false
```

La `condición` a evaluar es retorna un booleano al igual que en la condicional `if`. Las expresiones en caso de ser `true` o `false` se colocan en la misma línea sin necesidad de `else` separadas por dos puntos `:`.

```javascript
var speed = 120;
var message;

if(speed > 100) {
	message = "You're going too fast!";
} else {
	message = "Under the limit";
}

console.log(message);	// You're going too fast!
```

El código anterior lo podemos simplificar usando el operador ternario.

```javascript
var speed = 120;

var message = speed > 100 ? "You're going too fast!" : "Under the limit";

console.log(message);	// You're going too fast!
```

---

## Truthy y Falsy

En JavaScript todas las variables contienen un valor booleano, a esto se le conoce como `truthy` o `falsy`.

Los siguientes valores siempre son `falsy`:

- `false`
- `0`
- `''` o `""` - String vacío
- `null`
- `undefined`
- `NaN`

Todo lo demás es `truthy` incluyendo los siguientes casos:

- `'0'` - String conteniendo cero
- `'false'` - String con el texto `false`
- `[]` - Arreglo vacío
- `{}` - Objeto vacío
- `function(){}` - Función vacía

Esto es muy útil a la hora de usar condicionales pues podemos evaluar un sólo valor sin necesidad de operadores lógicos.

```javascript
if(value) {
	// value es truthy
} else {
	// value es falsy
	// puede ser false, 0, '', null, undefined o NaN
}
```

Es muy importante tener cuidado cuando se están haciendo comparaciones con `==` en lugar de `===` ya que se pueden obtener resultados inesperados, por ejemplo:

```javascript
[1] == '1' // true
```

En esta [tabla](https://dorey.github.io/JavaScript-Equality-Table/) se puede comparar los resultados de usar `==` con distintos valores.

---

## Bucles

Los ciclos o bucles ofrecen una manera rápida y sencilla de hacer algo repetidamente. Un ciclo `for` se repite hasta que la condición especificada se evalúa como `false`.

La sintaxis funciona de esta manera:

```javascript
for(var i = 0; i<=50; i++){
    // Código a ejecutar en cada ciclo
}
```

- `for`. La sintaxis para el inicio del ciclo. Posteriormente, abrimos paréntesis y dentro habrán 3 valores.  
- `Inicializador`. El primer valor en el cual declaras la variable, incluyendo con cuál número inicia el ciclo.
- `Condición`. El segundo valor es la condición, lo que tiene que pasar para terminar la iteración.
- `Incrementable`. El tercer valor es el incrementable. Cada vez que termina todas las sentencias de ejecución, la variable aumenta en 1. Esto se debe al operando `++`.

#### [Ejemplo 3: Ciclo `for`](./Ejemplo-03)

Otro ciclo es `while`, el cual se repite siempre y cuando la condición especificada sea evaluada como `true`.

```javascript
while(condición) {
	// Código a ejecutar en cada ciclo
}
```

El ejemplo 2 podría hacerse con `while` de la siguiente manera:

```javascript
var i = 0;

while(i <= 200) {
	console.log("Hello World");
	i++;
}
```

> Si olvidas incrementar la variable `i` dentro del `while` el ciclo nunca termina y se agotan los recursos de memoria.

#### [Reto 2: Números pares](./Reto-02)

#### [Reto 3: Números primos](./Reto-03)
