[`Programación con JavaScript`](../../Readme.md) > [`Sesión 11`](../Readme.md) > `Reto 02`

---

## Reto 3: Asynchronous Output

### Objetivos

Ejecutar múltiples procesos de manera asíncrona

#### Requisitos

`N/A`

#### Desarrollo

Completar la función `triggerActions` que pasa un callback a `processAction` para producir el siguiente resultado:

```javascript
"Processed Action 1"
"Processed Action 2"
"Processed Action 3"
...
"Processed Action n"
```

Se debe mostrar el mensaje _n_ cantidad de veces, determinado por `triggerActions`. Tomar en cuenta que no se debe
modificar la función `processAction`.

```javascript
// Don't alter this function
const processAction = (i, callback) => {
  setTimeout(function() {
    callback("Processed Action " + i);
  }, Math.random()*1000);
}

const triggerActions = (count) => {
  // Code goes here
}
```
