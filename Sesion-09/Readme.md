[`Programación con JavaScript`](../Readme.md) > `Sesión 09`

# Sesión 9: ECMAScript 6 (ES6 - ES2015)

## Objetivos

- Implementar las nuevas características de JavaScript en la creación, asignación de variables y uso de funciones de 
  flecha.

---

## Tabla de Contenidos

- **[¿Qué es ECMAScript 6?](#qué-es-ecmascript-6)**

- **[Template strings](#template-strings)**

- **[Spread operator](#spread-operator)**

  - [Copiar iterables](#copiar-iterables)

  - [Unir iterables](#unir-iterables)

  - [Rest parameter](#rest-parameter)

- **[Destructuring](#destructuring)**

  - [Reto 1: Intercambiar variables](./Reto-01/Readme.md)

  - [Ejemplo 1: Object destructuring](./Ejemplo-01/Readme.md)

  - [Reto 2: Objetos anidados](./Reto-02/Readme.md)

- **[Arrow functions](#arrow-functions)**

  - [Sintaxis](#sintaxis)

  - [Paréntesis](#paréntesis)

  - [Return implícito](#return-implícito)

  - [Funciones anónimas](#funciones-anónimas)

  - [Reto 3: Crear un número de teléfono](./Reto-03/Readme.md)

- **[Postwork](./Postwork/Readme.md)**

---

## ¿Qué es ECMAScript 6?

Ecma International es una organización sin ánimos de lucro encargada de regular el funcionamiento de
varios estándares en la industria de la computación. Así surge ECMAScript 1 (ES1) en 1997 como la primera
versión del estándar de JavaScript. Normalmente se usa el término ECMAScript para referirse al estándar
y JavaScript para hablar del lenguaje en la práctica.

En 2009 se lanzó ECMAScript 5 (ES5) con muchas mejoras de las versiones anteriores. Sin embargo, a los
navegadores les tomó varios años ser compatibles con esta versión.

En 2015 surge ECMAScript 2015, que también se le conoce como ES6 o ES2015. A partir de este año se decide
lanzar una nueva versión de manera anual cambiando el número del año en cada versión, es decir, ES2016,
ES2017, ES2018, etc.

Actualmente la versión ES5 es compatible con todos los navegadores. La versión ES6 es compatible con
navegadores modernos. Se puede usar la mayoría de las características de ES6 mediante un proceso de
transpiling y polyfilling que convierte el código en ES5, garantizando así la compatibilidad del código
en navegadores viejos.

---

## Template Strings

Las plantillas de texto o template strings, son cadenas de texto que permiten interpolación mediante expresiones. Hacen 
mucho más fácil crear textos en los que necesitamos integrar variables o expresiones. La sintaxis consta de dos partes, 
la primera es para delimitar la cadena de texto, se usan comillas invertidas. La segunda parte es para agregar 
placeholders mediante el uso del signo de dólar y llaves.

Normalmente si queremos agregar el valor de una variable a una cadena de texto debemos concatenar ambos con el signo +
y siempre tener cuidado de agregar espacios en blanco para que no salgan ambos textos juntos. Si usamos comillas
invertidas podemos incluir variables dentro del string.

```javascript
// ES5
const name = 'John Doe';

console.log("Welcome " + name); // Welcome John Doe

// ES6
const name = 'John Doe';

console.log(`Welcome ${ name }`); // Welcome John Doe
```

Estas plantillas hacen más fácil crear cadenas de string con múltiples líneas.

```javascript
const message = `Welcome Back!
John Doe
`;

console.log( message ); 
// Welcome Back!
// John Doe
```

Además de variables también podemos usar expresiones matemáticas.

```javascript
const a = 10;
const b = 20;

console.log(`a + b = ${a + b}`); // a + b = 30 
```

Trabajar con arreglos.

```javascript
const colors = ['blue', 'red', 'yellow'];

console.log(`Primary colors: ${ colors.join(', ') }`); // Primary colors: blue, red, yellow
```

Incluso funciones de alto orden.

```javascript
const numbers = [1, 2, 3, 4, 5, 6, 7, 8, 9, 10];

console.log(`Odd numbers: ${ 
  numbers.filter(function(n) { 
    return n % 2 !== 0 
  }) 
}`); // Odd numbers: 1,3,5,7,9
```

---

## Spread operator

El operador de propagación o spread operator hace más fácil trabajar con iterables como arreglos y objetos. La sintaxis
de este operador es `...` y se coloca justo antes de la variable.

### Copiar iterables

Uno de los usos más comunes de este operador es duplicar arreglos. Después de declarar el nombre de la variable usamos
corchetes para asignar un nuevo arreglo y dentro colocamos el spread operator para obtener todos los elementos del
arreglo que queremos copiar.

```javascript
const colors = ['blue', 'red', 'yellow'];
const copyOfColors = [ ...colors ];

console.log(copyOfColors); // ['blue', 'red', 'yellow']
```

En el caso de objetos es casi lo mismo, la única diferencia es el uso de llaves en lugar de corchetes.

```javascript
const book = {
  author: 'Marijn Haverbeke',
  title: 'Eloquent JavaScript',
  year: 2018
};
const copyOfBook = { ...book };

console.log(copyOfBook); 
// { author: "Marijn Haverbeke", title: "Eloquent JavaScript", year: 2018 }
```

### Unir iterables

También podemos usar el spread operator para concatenar arreglos.

```javascript
const oneToThree = [1, 2, 3];
const fourToSix = [4, 5, 6];
const oneToSix = [ ...oneToThree, ...fourToSix ]

console.log(oneToSix); // [1, 2, 3, 4, 5, 6]
```

Ahora `oneToSix` contiene todos los elementos de `oneToThree` y `fourToSix`. Además de concatenar arreglos podemos
usarlo para agregar nuevos elementos en un arreglo.

```javascript
const oneToThree = [1, 2, 3];
const oneToSix = [ ...oneToThree, 4, 5, 6 ]

console.log(oneToSix); // [1, 2, 3, 4, 5, 6]
```

Hay que tomar en cuenta que la posición donde se coloque el spread afecta el orden de los elementos en el arreglo.

```javascript
const oneToThree = [1, 2, 3];
const oneToSix = [ 4, 5, 6, ...oneToThree ]

console.log(oneToSix); // [4, 5, 6, 1, 2, 3]
```

Es muy similar en el caso de objetos.

```javascript
const formalGreetings = {
  english: 'Hello',
  french: 'Bonjour',
};

const informalGreetings = {
  russian: 'Privet',
  portuguese: 'Oi'
}

const greetings = { ...formalGreetings, ...informalGreetings }

console.log(greetings); 
// { english: "Hello", french: "Bonjour", russian: "Privet", portuguese: "Oi" }
```

En el caso de tener propiedades duplicadas se sobrescriben.

```javascript
const formalGreetings = {
  english: 'Hello',
  french: 'Bonjour',
};

const informalGreetings = {
  russian: 'Privet',
  portuguese: 'Oi'
}

const greetings = { 
  ...formalGreetings, 
  ...informalGreetings,
  english: 'Hi' 
}

console.log(greetings); 
// { english: "Hi", french: "Bonjour", russian: "Privet", portuguese: "Oi" }
```

Así como en los arreglos la posición del spread operator afecta el orden de los elementos, en los objetos el orden
del spread operator determina qué propiedad se sobrescribe.

```javascript
const formalGreetings = {
  english: 'Hello',
  french: 'Bonjour',
};

const informalGreetings = {
  russian: 'Privet',
  portuguese: 'Oi'
}

const greetings = { 
  english: 'Hi', 
  ...formalGreetings, 
  ...informalGreetings
}

console.log(greetings); 
// { english: "Hello", french: "Bonjour", russian: "Privet", portuguese: "Oi" }
```

### Rest parameter

Todas las funciones pueden ser llamadas con cualquier número de argumentos.

```javascript
function sum(a, b) {
  return a + b;
}

const total = sum(1, 2, 3, 4, 5); 
console.log(total); // 3
```

Esto no arroja ningún error, ya que los argumentos excedentes son ignorados, solo se toman en cuenta los dos primeros.
Usando la sintaxis del spread operator (`...`) podemos asignar cualquier cantidad de argumentos dentro de un arreglo.

```javascript
function sum(...numbers) {
  return numbers.reduce(function(prev, curr) {
    return prev + curr, 0 
  });
}

const total = sum(1, 2, 3, 4, 5); 
console.log(total); // 15
```

**Importante:** Spread operator y rest parameter tienen la misma sintaxis pero hacen lo opuesto. El primero nos permite 
extraer todos los elementos de un arreglo, mientras que el segundo crea un arreglo con todos los argumentos que recibe.

---

## Destructuring

Destructuring es extraer valores o propiedades de un arreglo u objeto.

```javascript
const colors = [ 'Red', 'Blue', 'Yellow' ]

const [ red, blue, yellow ] = colors;

console.log(red); // Red
console.log(blue); // Blue
console.log(yellow); // Yellow
```

En este ejemplo estamos creando 3 variables (`red`, `blue` y `yellow`) y asignando los valores del arreglo `colors`.
Esta asignación se hace basándose en el index del arreglo.

#### [Reto 1: Intercambiar variables](./Reto-01/Readme.md)

```javascript
const person = {
  firstName: 'John',
  lastName: 'Doe',
  country: 'Unknown'
};

const firstName = person.firstName;
const lastName = person.lastName;

console.log(firstName, lastName); // John Doe
```

Este es un caso muy común. En ocasiones queremos crear variables a partir de propiedades de un objeto. Podemos lograr
lo mismo en una sola línea.

```javascript
const person = {
  firstName: 'John',
  lastName: 'Doe',
  country: 'Unknown'
};

const { firstName, lastName } = person;

console.log(firstName, lastName); // John Doe
```

Las llaves del lado izquierdo del `=` no son un objeto. Esta es la sintaxis de object destructuring. Estamos creando dos
nuevas variables `firstName` y `lastName`, después estamos extrayendo dos propiedades de `person` con el mismo nombre de
las variables, el valor de esas propiedades es el que se asigna a las variables creadas.

#### [Ejemplo 1: Object destructuring](./Ejemplo-01/Readme.md)

#### [Reto 2: Objetos anidados](./Reto-02/Readme.md)

---

## Arrow functions

Las funciones de flecha o arrow functions es otra de las novedades de esta versión de JavaScript. Presentan una
sintaxis más concisa comparada con las funciones normales, también cuentas con `returns` implícitos y no cambian el
valor de `this`.

Antes de ver la sintaxis y cómo usar arrow functions veamos un ejemplo de un caso de uso de funciones normales.
Tenemos un arreglo `firstNames`.

```javascript
const firstNames = [ 'John', 'Jane', 'Mark'];
```

A cada nombre le vamos a agregar el apellido `Doe` y crear un nuevo arreglo `fullNames`. Una forma de hacerlo es con
un `map` y aprovechar la flexibilidad de los template strings.

```javascript
const firstNames = [ 'John', 'Jane', 'Mark'];

const fullNames = firstNames.map(function(name) {
  return `${name} Doe`;
});

console.log(fullNames); // ["John Doe", "Jane Doe", "Mark Doe"]
```

Ahora veamos cómo reescribir la función que recibe `map` como argumento y usar arrow function.

### Sintaxis

Para escribir arrow functions solo necesitamos eliminar el keyword `function` y agregar lo que se conoce como _fat
arrow_ (`=>`) después de los parámetros de la función.

```javascript
const firstNames = [ 'John', 'Jane', 'Mark'];

const fullNames = firstNames.map((name) => {
  return `${name} Doe`;
});

console.log(fullNames); // ["John Doe", "Jane Doe", "Mark Doe"]
```

La funcionalidad es exactamente la misma al ejemplo de más arriba.

### Paréntesis

La sintaxis de los arrow functions puede ser simplificada todavía más. Cuando solamente tenemos un parámetro en la
función podemos eliminar los paréntesis.

```javascript
const firstNames = [ 'John', 'Jane', 'Mark'];

const fullNames = firstNames.map(name => {
  return `${name} Doe`;
});

console.log(fullNames); // ["John Doe", "Jane Doe", "Mark Doe"]
```

Esta es una cuestión de estilo pues hay quienes prefieren siempre incluir los paréntesis aunque sea un solo parámetro.

### Return implícito

Cuando escribimos `return` estamos definiendo explícitamente lo que debe retornar la función. Muchas veces las funciones
solo retornan un valor sin hacer alguna otra operación antes. Cuando este es el caso podemos omitir el `return` pues el
arrow function asume que se va a retornar lo que sigue después del fat arrow.

```javascript
const firstNames = [ 'John', 'Jane', 'Mark'];

const fullNames = firstNames.map(name => `${name} Doe`);

console.log(fullNames); // ["John Doe", "Jane Doe", "Mark Doe"]
```

De esta manera podemos colocar todo en una sola línea, además de eliminar el `return` también debemos eliminar las
llaves (ya que estos definen un bloque de líneas). No es necesario definir que queremos retornar `${name} Doe`, esto
queda implícito.

### Funciones anónimas

Si usamos este tipo de funciones no podemos asignarle un nombre, ya que los arrow functions son funciones anónimas.
La forma más común de uso es asignar estas funciones a variables que sí podemos nombrar.

```javascript
const logName = name => console.log(`Hello ${name}!`);

logName('John Doe'); // Hello John Doe!
```

#### [Reto 3: Crear un número de teléfono](./Reto-03/Readme.md)

#### [Postwork](./Postwork/Readme.md)
