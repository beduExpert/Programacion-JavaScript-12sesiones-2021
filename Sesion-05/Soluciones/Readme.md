[`Programación con JavaScript`](../../Readme.md) > [`Sesión 05`](../Readme.md) > `Soluciones`

---

## Reto 1: Extraer una lista de propiedades

```javascript
function pluck(list, propertyName) {
  const values = [];

  for (let i = 0; i < list.length; i++) {
    values.push( list[i][propertyName] );
  }

  return values;
}
```

---

## Reto 2: Crear un número de teléfono

```javascript
function createPhoneNumber(numbers) {
  let format = '(xxx) xxx-xxxx'
  for (let num of numbers) {
    format = format.replace('x', num)
  }
  return format
}
```

---

## Reto 3: Encontrar elementos faltantes

```javascript
function findMissingNumbers(numbers) {
  const sortedArray = numbers.sort((a, b) => a - b)
  let missing = []
  for (let i = numbers[0]; i < numbers[sortedArray.length - 1]; i++) {
    if (sortedArray.indexOf(i) < 0) {
      missing.push(i);
    }
  }
  return missing
}
```
