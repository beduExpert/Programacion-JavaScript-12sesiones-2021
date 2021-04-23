[`Programación con JavaScript`](../../Readme.md) > [`Sesión 02`](../Readme.md) > `Reto 03`

---

## Reto 3: Números primos

### Objetivos

Dominar el uso de ciclos y operadores lógicos.

#### Requisitos

Haber terminado el [reto 2](../Reto-02).

#### Desarrollo

- Crear un ciclo desde 0 hasta 100.
- Mostrar todos los números primos en este ciclo con `console.log()`

> Un número primo es número natural mayor a 1 que sólo es divisible entre 1 y sí mismo.

<details>
  <summary>Solución</summary>

```javascript
for (var counter = 2; counter <= 100; counter++) {
  var isPrime = true;

  for (var i = 2; i <= counter; i++) {
    if (counter % i === 0 && i !== counter) {
      isPrime = false;
    }
  }

  if(isPrime) {
    console.log(counter);
  }
}
```
</details>
