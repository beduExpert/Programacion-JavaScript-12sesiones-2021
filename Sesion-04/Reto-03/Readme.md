[`Programación con JavaScript`](../../Readme.md) > [`Sesión 04`](../Readme.md) > `Reto 03`

---

## Reto 3: Fibonacci

### Objetivos

Implementar adecuadamente los conceptos vistos hasta el momento de funciones y ciclos para solucionar un problema.

#### Requisitos

Haber terminado el [reto 2](../Reto-02).

#### Desarrollo

En la serie de Fibonacci:

`1, 1, 2, 3, 5, 8, 13, 21, 34, 55, 89, 144...`

Cada elemento se obtiene sumando los dos valores anteriores.

Completar la función `fibonacciSequence` la cuál recibe `limit`, un entero positivo que representa la cantidad de
elementos de la serie que queremos.

```javascript
function fibonacciSequence(limit) {
  ...
}
```

La función debe mostrar en consola los elementos de la serie hasta que `limit` sea alcanzado.

```javascript
fibonacciSequence(1); // 1
fibonacciSequence(2); // 1, 1
fibonacciSequence(5); // 1, 1, 2, 3, 5
```
