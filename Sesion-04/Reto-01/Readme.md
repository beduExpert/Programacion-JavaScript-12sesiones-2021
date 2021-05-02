[`Programación con JavaScript`](../../Readme.md) > [`Sesión 03`](../Readme.md) > `Reto 01`

---

## Reto 1: Potenciación

### Objetivos

Implementar adecuadamente los conceptos vistos hasta el momento de funciones y ciclos para solucionar un problema.

#### Requisitos

`N/A`

#### Desarrollo

Crear una función `power` que recibe dos argumentos `base` y `exponent`. La función debe retornar el resultado de elevar `base` a la potencia `exponent`.

```javascript
function power(base, exponent) {
  ...
}
```

Recuerda que en la potenciación el `exponent` indica cuántas veces se debe multiplicar `base` por sí mismo.

```javascript
3 ^ 3 = 3 * 3 * 3
3 ^ 3 = 27
```

> Evitar usar el operador de exponenciación `**`

<details>
  <summary>Solución</summary>

```javascript
function power(base, exponent) {
  var result = 1;

  for(var i = 0; i < exponent; i++) {
    result *= base; // Same as: result = result * base;
  }

  return result;
}
```
</details>
