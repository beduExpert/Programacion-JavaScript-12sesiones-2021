[`Programación con JavaScript`](../../Readme.md) > [`Sesión 03`](../Readme.md) > `Reto 02`

---

## Reto 2: Número mayor

### Objetivos

Implementar adecuadamente los conceptos vistos hasta el momento de funciones y ciclos para solucionar un problema.

#### Requisitos

Haber terminado el [reto 1](../Reto-01).

#### Desarrollo

Completar la función `getLargerInt` la cual recibe dos números enteros. La función debe retornar el número mayor.

```javascript
function getLergerInt(number1, number2) {
  ...
}
```

<details>
  <summary>Solución</summary>

```javascript
function getLergerInt(number1, number2) {
  if(number1 > number2) {
    return number1
  } else {
    return number2
  }
}
```
</details>
