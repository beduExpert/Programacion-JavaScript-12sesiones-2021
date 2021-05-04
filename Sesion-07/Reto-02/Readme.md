[`Programación con JavaScript`](../../Readme.md) > [`Sesión 06`](../Readme.md) > `Reto 02`

---

## Reto 2: Compact

### Objetivos

Implementar funciones de alto orden para manipular arreglos.

#### Requisitos

Haber terminado el [Reto 1](../Reto-01/Readme.md).

#### Desarrollo

Crear una función `compact` que recibe un arreglo y retorna un nuevo arreglo sin incluir los valores que sean falsy.

```javascript
function compact(array) {
  ...
}

var array = [0, 1, false, 2, '', 3];
var compactedArray = compact(array);

console.log(compactedArray); // [1, 2, 3]
```

<details>
  <summary>Solución</summary>

```javascript
function compact(array) {
  return array.filter(function(element) {
    return !!element;
  });
}
```

</details>
