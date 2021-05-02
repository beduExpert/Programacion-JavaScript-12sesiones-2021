[`Programación con JavaScript`](../Readme.md) > `Sesión 03`

# Sesión 3: Objetos y Arreglos

## Objetivos

Mostrar las principales características de los objetos y arreglos, así como las diferencias con otros tipos de datos

---

## Tabla de Contenidos

- **[Arreglos](#arreglos)**

	- [Ejemplo 1: Arreglos](./Ejemplo-01)

	- [Reto 1: Calcular promedio](./Reto-01)

- **[Objetos](#objetos)**

	- [Ejemplo 2: Transformando objetos en arreglos](./Ejemplo-02)

	- [Reto 2: Arreglo a objeto](./Reto-02)

- **[Objetos y Métodos](#objetos-y-métodos)**

	- [Reto 3: Extraer una lista de propiedades](./Reto-03)

- **[Postwork](./Postwork/Readme.md)**

---

## Arreglos

Ya hemos trabajado con distintos tipos de datos como string, number y boolean. Muchas veces necesitamos representar una
colección de variables, en lugar de crear múltiples variables podemos utilizar arreglos.

```javascript
const color1 = 'Red';
const color2 = 'Blue';
const color3 = 'Green';

console.log(color1);	// Red
console.log(color2);	// Blue
console.log(color3);	// Green
```

En lugar de crear tres variables distintas podemos crear un arreglo usando corchetes `[]` y separando cada elemento del
arreglo con comas.

```javascript
const colors = ['Red', 'Blue', 'Green'];

console.log(colors);	// ['Red', 'Blue', 'Green']
```

Todo elemento de un arreglo tiene un identificador numérico que representa su posición en el arreglo. A esto se le
conoce como `index` y se empieza a contar desde cero.

![array](assets/array.png)

Este `index` nos permite acceder a un elemento específico del arreglo.

```javascript
const colors = ['Red', 'Blue', 'Green'];

console.log(colors[0]);	// 'Red'
console.log(colors[1]);	// 'Blue'
console.log(colors[2]);	// 'Green'
console.log(colors[3]);	// undefined
```

También se pueden manipular los elementos de un arreglo usando su `index`.

```javascript
const colors = ['Red', 'Blue', 'Green'];

console.log(colors);	// ['Red', 'Blue', 'Green']

colors[1] = 'Pink';

console.log(colors);	// ['Red', 'Pink', 'Green']
```

Para obtener la longitud del arreglo (cantidad de elementos) utilizamos el método `length`.

```javascript
const colors = ['Red', 'Blue', 'Green'];

console.log(colors);	// ['Red', 'Blue', 'Green']

console.log(colors.length);	// 3
```

#### [Ejemplo 1: Arreglos](./Ejemplo-01)

Una variación del ciclo `for` que hemos visto hasta ahora es el ciclo `for...of` que nos permite ejecutar un bloque de
código para cada elemento de un objeto iterable como es el caso de los arreglos. Retomemos el código final
del [ejemplo 1](./Ejemplo-01). 

```javascript
const numbers = [1, 3, 4, 7, 2, 1, 9, 0]

const doubled = []

for(let i = 0; i < numbers.length; i++) {
  doubled.push(numbers[i] * 2);
}

console.log(numbers); // [1, 3, 4, 7, 2, 1, 9, 0]
console.log(doubled);  // [2, 6, 8, 14, 4, 2, 18, 0]
```

Ahora podemos reescribir el ciclo usando `for...of`.

```javascript
const numbers = [1, 3, 4, 7, 2, 1, 9, 0]

const doubled = []

for(const number of numbers) {
  doubled.push(number * 2);
}

console.log(numbers)  // [1, 3, 4, 7, 2, 1, 9, 0]
console.log(doubled)  // [2, 6, 8, 14, 4, 2, 18, 0]
```

Para este ciclo se crea una variable en cada iteración que corresponde al elemento del arreglo. Es decir, `number` es
una variable creada en esa iteración cuyo valor es el equivalente a `numbers[i]`. Cuando usamos `for...of` también
podemos manipular las iteraciones con `break` y `continue` como lo vimos anteriormente.

```javascript
const numbers = [1, 3, 4, 7, 2, 1, 9, 0]

const doubled = []

for(const number of numbers) {
  if (number === 1) continue
  doubled.push(number * 2);
}

console.log(numbers)  // [1, 3, 4, 7, 2, 1, 9, 0]
console.log(doubled)  // [6, 8, 14, 4, 18, 0]
```

#### [Reto 1: Calcular promedio](./Reto-01)

---

## Objetos

En los arreglos utilizamos un índice numérico para acceder a un elemento de la colección. Con los objetos en lugar de usar valores numéricos como índice utilizamos propiedades con nombre y valor, el cual puede ser cualquier tipo de dato. Para crear un objeto utilizamos llaves `{}` separando cada propiedad con coma.

```javascript
var john = {
	firstName: 'John',
	lastName: 'Doe',
	birthYear: 1990
}
```

Se puede acceder al valor de una propiedad de dos formas. La primera es con un punto después del nombre del objeto seguido del nombre de la propiedad que queremos leer, la segunda es usando corchetes `[]` similar a como se hace con los arreglos pero pasando un string con el nombre de la propiedad en lugar de un `index`.

```javascript
var john = {
	firstName: 'John',
	lastName: 'Doe',
	birthYear: 1990
}

console.log(john.firstName);	// 'John'

console.log(john['lastName']);	// 'Doe'
```

De igual forma se puede cambiar el valor de las propiepdades de los objetos.

```javascript
var john = {
	firstName: 'John',
	lastName: 'Doe',
	birthYear: 1990
}

console.log(john.firstName);	// 'John'

john.firstName = 'Jane';

console.log(john.firstName);	// 'Jane'

john['firstName'] = 'Joe';

console.log(john['firstName']);	// 'Joe'
```

#### [Ejemplo 2: Transformando objetos en arreglos](./Ejemplo-02)

#### [Reto 2: Arreglo a objeto](./Reto-02)

---

## Objetos y métodos

Ya mencionamos que las propiedades de los objetos pueden contener cualquier tipo
de dato, esto incluye expresiones de funciones, en cuyo caso deja de llamarse propiedad
y se conoce como método.

```javascript
var john = {
	firstName: 'John',
	lastName: 'Doe',
	birthYear: 1990,
	calculateAge: function(birthYear) {
		var today = new Date();
		var year = today.getFullYear();

		return year - birthYear;
	}
}
```

Acabamos de agregar el método `calculateAge`, como vemos es una expresión de función,
una función anónima que recibe `birthYear` como argumento. Este método nos regresa
la edad actual de John.

```javascript
console.log( john.calculateAge(1990) );	// 30
```

La variable `today` es un objeto de la clase `Date()` de JavaScript. A su vez vemos
que este objeto tiene un método `getFullYear()` el cual nos regresa el año.

No necesitamos pasar el argumento `birthYear` al método `calculateAge` porque ya existe
como propiedad del objeto `john`.

```javascript
var john = {
	firstName: 'John',
	lastName: 'Doe',
	birthYear: 1990,
	calculateAge: function() {
		var today = new Date();
		var year = today.getFullYear();

		return year - this.birthYear;
	}
}
```

El keyword `this` hace referencia al mismo objeto, por lo que cuando decimos `this.birthYear`
es como decir `john.birthYear`. Lo usamos cuando queremos hacer referencia a
una propiedad o método del mismo objeto, e incluso para asignar nuevas propiedades.

```javascript
var john = {
	firstName: 'John',
	lastName: 'Doe',
	birthYear: 1990,
	calculateAge: function() {
		var today = new Date();
		var year = today.getFullYear();

		this.age = year - this.birthYear;
	}
}
```

Ahora el método `calculateAge` en lugar de retornar la edad la va a guardar en una nueva
propiedad llamada `age.`

```javascript
console.log( john );
/*
Valor actual
{
  firstName: "John",
  lastName: "Doe",
  birthYear: 1990,
  calculateAge: ƒ
}
*/

john.calculateAge();

console.log( john );
/*
Después de llamar el método calculateAge()
{
  firstName: "John",
  lastName: "Doe",
  birthYear: 1990,
  age: 30,
  calculateAge: ƒ
}
*/
```

#### [Reto 3: Extraer una lista de propiedades](./Reto-03)

En este punto nos damos cuenta que los arreglos también tienen métodos como `push()` que agrega un elemento al final del arreglo o `pop()` que elimina el último elemento del arreglo. También los strings tienen propiedades como `length` que retorna la longitud del string, o incluso métodos como `search()` que permite buscar un valor específico dentro del string. Por eso es común escuchar que todo en JavaScript se comporta como un objeto.
