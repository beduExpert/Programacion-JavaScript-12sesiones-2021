[`Programación con JavaScript`](../../Readme.md) > [`Sesión 02`](../Readme.md) > `Reto 01`

---

## Reto 1: Operadores lógicos - if/else

### Objetivos

Implementar adecuadamente los operadores lógicos necesarios para controlar el flujo del código.

#### Requisitos

Vamos a empezar con el último código generado en el [Ejemplo 01](../Ejemplo-01/):

```javascript
var time = 13;
var greeting;

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

Nuestro código tiene una pequeña falla, el día sólo tiene 24 horas y no se está tomando en cuenta el caso en el que `time` sea una hora inválida.

Utilizando lo visto hasta el momento sobre operadores lógicos y condicionales, debes crear un nuevo mensaje que será usado cuando `time` sea una hora que no existe en el día.

<details>
  <summary>Solución</summary>

```javascript
var time = 27;
var greeting;

if (time >= 0 && time < 12) {
  greeting = "Good morning";
} else if (time >= 12 && time < 20) {
  greeting = "Good afternoon";
} else if (time >= 20 && time < 24) {
  greeting = "Good evening";
} else {
  greeting = "Unknown hour";
}

console.log(greeting) // Unknown hour
```
</details>
