[`Programación con JavaScript`](../../Readme.md) > [`Sesión 02`](../Readme.md) > `Reto 02`

---

## Reto 2: Números pares

### Objetivos

Dominar el uso de ciclos y operadores lógicos.

#### Requisitos

`N/A`

#### Desarrollo

- Crear un ciclo desde 0 hasta 100.
- Mostrar todos los números pares en este ciclo con `console.log()`

<details>
  <summary>Solución</summary>

```javascript
for(var i = 0; i <= 100; i++) {
  if(i % 2 === 0) {
    console.log( i );
  }
}
```
</details>
