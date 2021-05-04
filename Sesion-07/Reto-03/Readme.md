[`Programación con JavaScript`](../../Readme.md) > [`Sesión 06`](../Readme.md) > `Reto 03`

---

## Reto 3: Loop

### Objetivos

Implementar funciones de alto orden para manipular arreglos.

#### Requisitos

Haber terminado el [Reto 2](../Reto-02/Readme.md).

#### Desarrollo

Crear una función de alto orden `loop` que será similar a un `for`. Recibe `value`, una función `test`, una función `update` y una función `body`. En cada iteración se debe ejecutar la función `test` y terminar el ciclo si la función retorna `false`. Después se ejecuta la función `body` dándole como argumento el `value` actual. Por último se ejecuta la función `update` para crear un nuevo valor y se repite el proceso.

```javascript
function loop(start, test, update, body) {
  ...
}

var test = function(n) {
  return n > 0;
}

var update = function(n) {
  return n - 1;
}

loop(3, test, update, console.log);
// 3
// 2
// 1
```

<details>
  <summary>Solución</summary>

```javascript
function loop(start, test, update, body) {
  for (var value = start; test(value); value = update(value)) {
    body(value);
  }
}
```

</details>
