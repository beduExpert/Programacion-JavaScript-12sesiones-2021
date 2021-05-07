[`Programación con JavaScript`](../../Readme.md) > [`Sesión 05`](../Readme.md) > `Ejemplo 01`

---

## Ejemplo 1: Block scope

### Objetivo

Diferenciar function scope de block scope

#### Requisitos

En una nueva carpeta vamos a crear un archivo `HTML` en blanco llamado `index.html`:

```html
<html lang="es">
  <head>
    <meta charset="utf-8"/>
    <title>Ejemplo 1: Block Scope</title>
  </head>
  <body>
    <script type="text/javascript" src="./ejemplo-1.js"></script>
  </body>
</html>
```

Dentro de la misma carpeta creamos un archivo `ejemplo-1.js` que es donde se trabajarán los ejemplos de esta sesión.
Finalmente abre el archivo `index.html` en Chrome e inspecciona la consola para ver los resultados.

#### Desarrollo

Cuando agrupamos una o varias sentencias dentro de un par de llaves decimos que tenemos Block Statements o bloque de
sentencias. Esto lo usamos todo el tiempo, en funciones por ejemplo, lo usamos para delimitar el cuerpo de la función.
También lo usamos en condicionales como `if/else` o `switch`, e incluso en bucles como `for` o `while`.

Aquí encontramos otra diferencia entre `var` y `let/const`. Un bloque de sentencias no genera un nuevo scope local
cuando estamos usando `var`.

```javascript
if(true) {
  var foo = "John Doe"

  console.log(foo) // "John Doe"
}

console.log(foo) // "John Doe"
```

En este bloque `if` creamos una variable `foo`, como `var` no tiene block scope se encuentra en el scope global, es por
eso que podemos llamar a `foo` desde afuera del bloque.

```javascript
var numbers = [1, 2, 3, 4, 5]
var doubles = []

for(var i = 0; i < numbers.length; i++) {
  doubles.push(numbers[i] * 2)
}

console.log(numbers) // [1, 2, 3, 4, 5]
console.log(doubles) // [2, 4, 6, 8, 10]
console.log(i) // 5
```

Este es otro ejemplo, en este bloque `for` creamos un contador `i` que cuenta con scope global por lo que es accesible
desde otras partes del código.

Ahora bien, las variables creadas con `let/const` cuentan con block scope, es decir, su scope está limitado al bloque
donde son creadas dichas variables. 

```javascript
if(true) {
  const foo = "John Doe"

  console.log(foo) // "John Doe"
}

console.log(foo) // Uncaught ReferenceError: foo is not defined
```

Ahora `foo` no puede leerle fuera del `if` en el que fue creado. Lo mismo sucede para el ciclo `for` que hicimos
anteriormente.

```javascript
const numbers = [1, 2, 3, 4, 5]
const doubles = []

for(let i = 0; i < numbers.length; i++) {
  doubles.push(numbers[i] * 2)
}

console.log(numbers) // [1, 2, 3, 4, 5]
console.log(doubles) // [2, 4, 6, 8, 10]
console.log(i) // Uncaught ReferenceError: i is not defined
```
