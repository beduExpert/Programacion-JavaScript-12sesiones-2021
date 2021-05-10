[`Programación con JavaScript`](../../Readme.md) > [`Sesión 07`](../Readme.md) > `Reto 03`

---

## Reto 3: Loop

### Objetivos

Implementar funciones de alto orden para manipular arreglos.

#### Requisitos

Haber terminado el [Reto 2](../Reto-02/Readme.md).

#### Desarrollo

Crear una función de alto orden `loop` que será similar a un `for`. 

Recibe tres argumentos: `start`, una función `test`, una función `update` y una función `body`. 

- El ciclo empieza en `start` y termina cuando `test` retorne `false`.
- En cada iteración se ejecuta la función `body` dándole como argumento el valor actual de `start` actual. 
- Al final de cada ciclo se ejecuta la función `update`.

```javascript
function loop(start, test, update, body) {
  // Code goes here...
}

const test = function(n) {
  return n > 0;
}

const update = function(n) {
  return n - 1;
}

loop(3, test, update, console.log);
// 3
// 2
// 1
```
