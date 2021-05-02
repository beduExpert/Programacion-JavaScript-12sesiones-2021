[`Programación con JavaScript`](../../Readme.md) > [`Sesión 03`](../Readme.md) > `Reto 02`

---

## Reto 2: Arreglo a objeto

### Objetivos

Implementar adecuadamente los conceptos vistos hasta el momento de arreglos y ciclos para solucionar un problema.

#### Requisitos

En el ejemplo 2 transformamos un objeto a un arreglo con los pares `[key, value]` por cada propiedad y valor del objeto.

```javascript
const car = {
  brand: 'Nissan',
  model: 'Versa',
  year: 2020
}

const keys = Object.keys(car)
const pairs = []

for(let i = 0; i < keys.length; i++) {
  pairs.push( [keys[i], car[keys[i]]] )
}

console.log(pairs)

// [['brand', 'Nissan'], ['model', 'Versa'], ['year', 2020]]
```

#### Desarrollo

Para este reto vamos a realizar lo opuesto. Es decir, tomar un arreglo con pares `[key, value]` y crear un objeto con
sus respectivas propiedades y valores.

```javascript
const car = [['brand', 'Nissan'], ['model', 'Versa'], ['year', 2020]]
```
