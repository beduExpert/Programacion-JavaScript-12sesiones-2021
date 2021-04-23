[`Programación con JavaScript`](../../Readme.md) > [`Sesión 04`](../Readme.md) > `Reto 01`

---

## Reto 1: Calcular promedio

### Objetivos

Implementar adecuadamente los conceptos vistos hasta el momento de funciones y ciclos para solucionar un problema.

#### Requisitos

`N/A`

#### Desarrollo

Completar la función `calculateAverage` la cual recibe `numbers`, un arreglo de _n_ cantidad de enteros. La función debe retornar el promedio de todos los enteros que tenga `numbers`.

```javascript
function calculateAverage(numbers) {
  ...
}
```

> Para calcular el promedio se divide la suma de todos los elementos entre el número total de elementos.

<details>
  <summary>Solución</summary>

```javascript
function calculateAverage(numbers) {
  var sum = 0;

  for (var i = 0; i < numbers.length; i++) {
    sum += numbers[i]; // Same as: sum = sum + numbers[i];
  }

  return sum / numbers.length
}
```
</details>
