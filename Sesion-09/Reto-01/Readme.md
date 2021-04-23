[`Programación con JavaScript`](../../Readme.md) > [`Sesión 09`](../Readme.md) > `Reto 01`

---

## Reto 1: Intercambiar variables

### Objetivos

Implementar asignación por destructuring para intercambiar variables

#### Requisitos

`N/A`

#### Desarrollo

Cuando necesitamos intercambiar el valor de dos variables usualmente usamos una tercera variable temporal.

```javascript
let person1 = 'John Doe';
let person2 = 'Jane Doe';

let tmp = person1;
person1 = person2;
person2 = tmp;

console.log(`Person 1: ${person1}
Person 2: ${person2}`); 
// Jane Doe
// John Doe
```

- Obtener el mismo resultado implementando asignación por destructuring.

Podemos hacer lo mismo con arreglos:

```javascript
const colors = [ 'Red', 'Blue', 'Yellow' ];
```

- Intercambiar los valores del primer elemento del arreglo con el último elemento.

<details>
  <summary>Solución</summary>

```javascript
// Obtener el mismo resultado implementando asignación por destructuring.
[ person1, person2 ] = [ person2, person1 ];

// Intercambiar los valores del primer elemento del arreglo con el último elemento.
[ colors[0], colors[2] ] = [ colors[2], colors[0] ]
```

</details>
