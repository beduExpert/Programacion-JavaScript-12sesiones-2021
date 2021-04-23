[`Programación con JavaScript`](../../Readme.md) > [`Sesión 09`](../Readme.md) > `Reto 03`

---

## Reto 3: Crear un número de teléfono

### Objetivos

Implementar ciclos o funciones de alto orden para producir un string con formato especificado

#### Requisitos

`N/A`

#### Desarrollo

Escribir una función que reciba un arreglo de 10 enteros entre 0 - 9, y retorne un string en forma de número telefónico.

```javascript
createPhoneNumber([1, 2, 3, 4, 5, 6, 7, 8, 9, 0]); // "(123) 456-7890"
```

La función debe retornar el mismo formato, incluyendo el espacio después del paréntesis.

<details>
  <summary>Solución</summary>

```javascript
// for...of.
function createPhoneNumber(numbers) {
  let format = '(xxx) xxx-xxxx'
  for (let num of numbers) {
    format = format.replace('x', num)
  }
  return format
}

// reduce()
const createPhoneNumber = (numbers) => 
  numbers.reduce((accumulator, current) => 
    accumulator.replace('x', current), '(xxx) xxx-xxxx')
```

</details>
