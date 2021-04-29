[`Programación con JavaScript`](../Readme.md) > `Sesión 02`

---

# Sesión 2: Controles de flujo

## Objetivos

Distinguir las distintas estructuras que permiten controlar el flujo de ejecución de un programa o aplicación

---

## Tabla de Contenidos

- **[Condicionales](#condicionales)**
	- [Operadores de comparación](#operadores-de-comparación)
	- [Operadores lógicos](#operadores-lógicos)
	- [`if`/`else`](#if--else)
		- [Ejemplo 1: Primeras condicionales](./Ejemplo-01)
		- [Reto 1: Controles de flujo](./Reto-01)
	- [`switch`](#switch)
		- [Ejemplo 2: Usando `switch`](./Ejemplo-02)
- **[Operador Ternario](#operador-ternario)**
- **[Truthy y Falsy](#truthy-y-falsy)**
- **[Bucles](#bucles)**
	- [Break y Continue](#break-y-continue)
	- [Ejemplo 3: Ciclo `for`](./Ejemplo-03)
	- [Reto 2: Números pares](./Reto-02)
	- [Reto 3: Números primos](./Reto-03)

---

## Condicionales

Las condicionales nos permiten controlar el flujo de un programa, es decir, podemos controlar las partes del código que
se ejecutarán dependiendo de si una condición se cumple o no.

### Operadores de comparación

| Operador | Descripción                                                                                               | Ejemplo            |
|----------|-----------------------------------------------------------------------------------------------------------|--------------------|
|    ==    | **Igualdad:** Devuelve `true` si ambos operandos son iguales                                              | 3 == 3<br>3 == '3' |
|    !=    | **Desigualdad:** Devuelve `true` si los operandos no son iguales                                          |       3 != 4       |
|    ===   | **Estrictamente iguales:** Devuelve `true` si los operandos son igual y tienen el mismo tipo.             |       3 === 3      |
|    !==   | **Estrictamente desiguales:** Devuelve `true` si los operandos no son iguales y/o no son del mismo tipo.  |      3 !== '3'     |
|     >    | **Mayor que:** Devuelve `true` si el operando de la izquierda es mayor que el operando de la derecha.     |        4 > 3       |
|    >=    | **Mayor o igual que:** Devuelve `true` si el operando izquierdo es mayor o igual que el operando derecho. |       4 >= 4       |
|     <    | **Menor que:** Devuelve `true` si el operando izquierdo es menor que el operando derecho.                 |       12 < 15      |
|    <=    | **Menor o igual que:** Devuelve `true` si el operando izquierdo es menor o igual que el operando derecho. |      12 <= 12      |

### Operadores lógicos

Los operadores lógicos se utilizan normalmente con valores booleanos (lógicos); cuando lo son, devuelven un valor
booleano. Sin embargo, los operadores `&&` y `||` en realidad devuelven el valor de uno de los operandos especificados,
por lo que si estos operadores se utilizan con valores no booleanos, pueden devolver un valor no booleano.

| Operador | Descripción                                                                                            |
|:--------:|--------------------------------------------------------------------------------------------------------|
|    &&    | **And:** Devuelve `true` si ambos operandos son `true`.                                                |
|   \|\|   | **Or:** Devuelve `true` si algunos de los operandos es `true`.                                         |
|     !    | **Not:** Devuelve `false` si su único operando puede convertirse a `true`.                             |
|    ??    | **Nullish:** Devuelve la parte derecha del operador cuando la parte izquierda es `null` o `undefined`. |

#### Logical AND (&&)

```javascript
const a1 =  true && true;     // t && t devuelve true
const a2 =  true && false;    // t && f devuelve false
const a3 = false && true;     // f && t devuelve false
const a4 = false && (3 == 4); // f && f devuelve false
const a5 = 'Cat' && 'Dog';    // t && t devuelve Dog
const a6 = false && 'Cat';    // f && t devuelve false
const a7 = 'Cat' && false;    // t && f devuelve false
```

#### Logical OR (||)

```javascript
const o1 =  true || true;     // t || t devuelve true
const o2 = false || true;     // f || t devuelve true
const o3 =  true || false;    // t || f devuelve true
const o4 = false || (3 == 4); // f || f devuelve false
const o5 = 'Cat' || 'Dog';    // t || t devuelve Cat
const o6 = false || 'Cat';    // f || t devuelve Cat
const o7 = 'Cat' || false;    // t || f devuelve Cat
```

#### Logical NOT (!)

```javascript
const n1 = !true;  // !t devuelve false
const n2 = !false; // !f devuelve true
const n3 = !'Cat'; // !t devuelve false
```

#### Nullish coalescing operator (??)

```javascript
const x1 = false ?? 'Cat';  // f ?? t devuelve false
const x2 = null ?? 'Cat';   // null ?? t devuelve Cat
const x2 = 0 ?? 'Cat';      // f ?? t devuelve Cat
```

---

### `if` / `else`

El tipo de condición más común de todos. Traducida literalmente del inglés, se la podría llamar la estructura *si...si
no*, es decir, *si se cumple la condición, haz esto, y sino, haz esto otro*.

La sintaxis se compone de la siguiente forma:

```javascript
if ( /* Condición a evaluar */ ) {
  // Código a ejecutar si la condición retorna true
} else {
  // Código a ejecutar si la condición retorna false
}
```

- `if` - La palabra clave que indica que se va a realizar una condicional.
- `( ... )` - Dentro de los paréntesis se coloca la condición a evaluar, la cual retorna un booleano, es decir, `true`
	o `false`.
- `{ ... }` - Dentro de las llaves va el texto a ejecutar en caso de que la condición sea `true`.
- `else` - Se utiliza para controlar el flujo en caso de que la condición sea `false`. Si se usa `else`, el código
	dentro de las llaves que le siguen se ejecuta solo cuando la condición anterior no se cumplió.

#### [Ejemplo 1: Primeras condicionales](./Ejemplo-01)

#### [Reto 1: Controles de flujo](./Reto-01)

### `switch`

Esta condicional nos permite ejecutar un solo bloque de código de varios. Es una buena alternativa cuando tenemos
múltiples condicionales `if`/`else`.

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

El operador ternario es el único operador en JavaScript que consta de tres operandos. Es una buena alternativa para una
condición `if`/`else`, ya que presenta una sintaxis más sencilla.

```javascript
condición ? expresión_true : expresión_false
```

La `condición` a evaluar retorna un booleano al igual que en la condicional `if`. Las expresiones en caso de
ser `true` o `false` se colocan en la misma línea sin necesidad de `else` separadas por dos puntos `:`.

```javascript
const speed = 120
let message

if(speed > 100) {
  message = "You're going too fast!"
} else {
  message = "Under the limit"
}

console.log(message)	// You're going too fast!
```

El código anterior lo podemos simplificar usando el operador ternario.

```javascript
const speed = 120

const message = speed > 100 ? "You're going too fast!" : "Under the limit"

console.log(message)	// You're going too fast!
```

En el ejemplo anterior usamos el operador ternario para asignar un valor dependiendo del resultado de la evaluación
de `speed > 100`. Por ello, es común caer en el siguiente error cuando queremos asignar un booleano condicionalmente:

```javascript
const speed = 120

const isFast = speed > 100 ? true : false

console.log(isFast);	// true
```

En este caso no es necesario un operador ternario porque la expresión `speed > 100` se evalúa en un booleano por lo que
podemos simplificar el código.

```javascript
const speed = 120

const isFast = speed > 100

console.log(isFast);	// true
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

Esto es muy útil a la hora de usar condicionales pues podemos evaluar un solo valor sin necesidad de operadores lógicos.

```javascript
if(value) {
  // value es truthy
} else {
  // value es falsy
  // puede ser false, 0, '', null, undefined o NaN
}
```

Es muy importante tener cuidado cuando se están haciendo comparaciones con `==` en lugar de `===` ya que se pueden
obtener resultados inesperados, por ejemplo:

```javascript
[1] == '1' // true
```

En esta [tabla](https://dorey.github.io/JavaScript-Equality-Table/) se puede comparar los resultados de usar `==` con
distintos valores.

---

## Bucles

Los ciclos o bucles ofrecen una manera rápida y sencilla de hacer algo repetidamente. Un ciclo `for` se repite hasta que
la condición especificada se evalúa como `false`.

La sintaxis funciona de esta manera:

```javascript
for(let i = 0; i<=50; i++){
  // Código a ejecutar en cada ciclo
}
```

- `for`: La sintaxis para el inicio del ciclo. Posteriormente, abrimos paréntesis y dentro habrá 3 valores.
- `Inicializador`: El primer valor en el cual declaras la variable, incluyendo con cuál número inicia el ciclo.
- `Condición`: El segundo valor es la condición, lo que tiene que pasar para terminar la iteración.
- `Incrementable`: El tercer valor es el incrementable. Cada vez que termina todas las sentencias de ejecución, la
	variable aumenta en 1. Esto se debe al operando `++`.

#### [Ejemplo 3: Ciclo `for`](./Ejemplo-03)

Otro ciclo es `while`, el cual se repite siempre y cuando la condición especificada sea evaluada como `true`.

```javascript
while(condición) {
  // Código a ejecutar en cada ciclo
}
```

El ejemplo 2 podría hacerse con `while` de la siguiente manera:

```javascript
let i = 0;

while(i <= 200) {
  console.log("Hello World");
  i++;
}
```

> Si olvidas incrementar la variable `i` dentro del `while` el ciclo nunca termina y se agotan los recursos de memoria.

### Break y continue

Ya vimos que `break` puede ser usado en `switch` para salir del bloque condicional. Este también puede ser usado para
salir de un bucle.

```javascript
for (let i = 0; i < 10; i++) {
  if (i === 3) break
  console.log(`Number: ${i}`)
}
```

En este ejemplo `break` termina el bucle cuando el contador `i` es igual a 3. Por otro lado, `continue` no detiene el
bucle, solo se brinca una iteración y continúa con el ciclo.

```javascript
for (let i = 0; i < 10; i++) {
  if (i === 3) continue
  console.log(`Number: ${i}`)
}
```

#### [Reto 2: Números pares](./Reto-02)

#### [Reto 3: Números primos](./Reto-03)
