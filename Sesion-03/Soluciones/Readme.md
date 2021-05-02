[`Programación con JavaScript`](../../Readme.md) > [`Sesión 03`](../Readme.md) > `Soluciones`

---

## Reto 1: Calcular promedio

```javascript
const numbers = [5, 3, 4, 7, 2, 1, 9, 7, 7]
let sum = 0;

for (const num of numbers) {
  sum += num; // Same as: sum = sum + numbers[i];
}

const average = sum / numbers.length

console.log(average)  // 5
```

---

## Reto 2: Arreglo a objeto

```javascript
const car = [['brand', 'Nissan'], ['model', 'Versa'], ['year', 2020]]
const obj = {}

for(const keyValue of car) {
  obj[keyValue[0]] = keyValue[1]
}

console.log(obj)
```

---

## Reto 3: Objetos anidados

```javascript
const person = {
  firstName: 'John',
  lastName: 'Doe',
  links: {
    web: {
      blog: 'https://johndoe.com'
    },
    social: {
      facebook: 'https://facebook.com/john.doe',
      instagram: 'https://instagram.com/john.doe'
    }
  }
}

const { facebook: fb, instagram: ig } = person.links.social
```
