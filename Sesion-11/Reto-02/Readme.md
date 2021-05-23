[`Programación con JavaScript`](../../Readme.md) > [`Sesión 11`](../Readme.md) > `Reto 02`

---

## Reto 2: Llamar función async

### Objetivos

Ejecutar una función `async` desde una función normal

#### Requisitos

`N/A`

#### Desarrollo

La siguiente función `async` espera un segundo antes de retornar un string `Hello World`. ¿Cómo podemos llamarla desde
una función que no es `async` y usar el valor que resuelve la promesa para mostrarlo en consola sin usar `await`?

```javascript
async function wait() {
  await new Promise(resolve => setTimeout(resolve, 1000));

  return 'Hello World';
}

function log(value) {
  // Code goes here...
}

log()
```
