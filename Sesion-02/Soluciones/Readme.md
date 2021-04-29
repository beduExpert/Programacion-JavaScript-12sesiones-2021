[`Programación con JavaScript`](../../Readme.md) > [`Sesión 02`](../Readme.md) > `Soluciones`

---

## Reto 1: Operadores condicionales

```javascript
const time = 27;
let greeting;

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

---

## Reto 2: Números pares

```javascript
for(let i = 0; i <= 100; i++) {
  if(i % 2 === 0) console.log( i )
}
```

---

## Reto 3: Números primos

```javascript
for (let counter = 2; counter <= 100; counter++) {
  let isPrime = true;

  for (let i = 2; i <= counter; i++) {
    if (counter % i === 0 && i !== counter) {
      isPrime = false;
    }
  }

  if(isPrime) console.log(counter)
}
```
