[`Programación con JavaScript`](../../Readme.md) > [`Sesión 04`](../Readme.md) > `Reto 02`

---

## Reto 2: Arreglo a objeto

### Objetivos

Implementar adecuadamente los conceptos vistos hasta el momento de funciones y ciclos para solucionar un problema.

#### Requisitos

En el Ejemplo 2 se creó una función para transformar un objeto en un arreglo con los pares
`[key, value]` por cada propiedad.

```javascript
function keyValuePairs(obj) {
    var keys = Object.keys(obj);
    var pairs = [];

    for(var i = 0; i < keys.length; i++) {
      pairs.push( [keys[i], obj[keys[i]]] )
    }

    return pairs;
}
```

#### Desarrollo

Para este reto vamos a crear una función que haga lo opuesto. Es decir, la función recibe
un arreglo con pares `[key, value]` y debe retornar un objeto con sus respectivas propiedades
y valores.

<details>
  <summary>Solución</summary>

```javascript
function arrayToObject(arr) {
  var obj = {};

  for(var i = 0; i < arr.length; i++) {
    obj[arr[i][0]] = arr[i][1]
  }

  return obj;
}
```
</details>
