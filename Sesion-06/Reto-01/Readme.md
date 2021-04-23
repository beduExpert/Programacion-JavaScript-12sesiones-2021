[`Programación con JavaScript`](../../Readme.md) > [`Sesión 06`](../Readme.md) > `Reto 01`

---

## Reto 1: Flatten

### Objetivos

Implementar funciones de alto orden para manipular arreglos.

#### Requisitos

`N/A`

#### Desarrollo

Crear una función `flatten` que recibe un arreglo de arreglos y retorna un nuevo arreglo con todos los elementos del arreglo original.

```javascript
function flatten(arrays) {
  ...
}

var arrays = [[1, 2, 3], [4, 5], [6]];
var array = flatten(arrays);

console.log(array); // [1, 2, 3, 4, 5, 6]
```

<details>
  <summary>Solución</summary>

```javascript
function flatten(arrays) {
  return arrays.reduce(function(flat, current) {
    return flat.concat(current);
  }, []);
}
```

</details>
