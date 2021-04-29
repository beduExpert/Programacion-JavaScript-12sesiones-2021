[`Programación con JavaScript`](../../Readme.md) > [`Sesión 02`](../Readme.md) > `Reto 01`

---

## Reto 1: Operadores condicionales

### Objetivos

Implementar adecuadamente los operadores condicionales necesarios para controlar el flujo del código.

#### Requisitos

Vamos a empezar con el último código generado en el [Ejemplo 01](../Ejemplo-01/):

```javascript
const time = 13;
let greeting;

if (time < 12) {
  greeting = "Good morning";
} else if (time < 20) {
  greeting = "Good afternoon";
} else if (time >= 20) {
  greeting = "Good evening";
}

console.log(greeting) // Good afternoon
```

#### Desarrollo

Nuestro código tiene una pequeña falla, el día solo tiene 24 horas y no se está tomando en cuenta el caso en el
que `time` sea una hora inválida.

Utilizando lo visto hasta el momento sobre operadores lógicos y condicionales, debes crear un nuevo mensaje que será
usado cuando `time` sea una hora que no existe en el día.
