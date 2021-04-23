[`Programación con JavaScript`](../../Readme.md) > [`Sesión 04`](../Readme.md) > `Reto 03`

---

## Reto 3: Extraer una lista de propiedades

### Objetivos

Implementar adecuadamente los conceptos vistos hasta el momento de funciones y ciclos para solucionar un problema.

#### Requisitos

`N/A`

#### Desarrollo

Completar la función `pluck` que extrae una lista de propiedades de un arreglo de objetos.

```javascript
var singers = [
  { name: 'Steven Tyler', band: 'Aerosmith', born: 1948 },
  { name: 'Karen Carpenter', band: 'The Carpenters', born: 1950 },
  { name: 'Kurt Cobain', band: 'Nirvana', born: 1967 },
  { name: 'Chris Cornell', band: 'Soundgarden', born: 1964 },
];

function pluck(list, propertyName) {
  ...
}

console.log( pluck(singers, 'name') );
// ["Steven Tyler", "Karen Carpenter", "Kurt Cobain", "Chris Cornell"]

console.log( pluck(singers, 'band') );
// ["Aerosmith", "The Carpenters", "Nirvana", "Soundgarden"]

console.log( pluck(singers, 'born') );
// [1948, 1950, 1967, 1964]
```

<details>
  <summary>Solución</summary>

```javascript
function pluck(list, propertyName) {
  var values = [];

  for (var i = 0; i < list.length; i++) {
    values.push( list[i][propertyName] );
  }

  return values;
}
```
</details>
