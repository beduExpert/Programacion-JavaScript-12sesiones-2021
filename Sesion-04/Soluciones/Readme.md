[`Programación con JavaScript`](../../Readme.md) > [`Sesión 04`](../Readme.md) > `Soluciones`

---

## Reto 1: Potenciación

```javascript
function power(base, exponent) {
  let result = 1;

  for(var i = 0; i < exponent; i++) {
    result *= base; // Same as: result = result * base;
  }

  return result;
}
```

---

## Reto 2: Número mayor

```javascript
function getLergerInt(number1, number2) {
  if(number1 > number2) {
    return number1
  } else {
    return number2
  }
}
```

---

## Reto 3: Fibonacci

```javascript
function fibonacci(num) {
  if (num <= 1) return 1;

  return fibonacci(num - 1) + fibonacci(num - 2);
}

function fibonacciSequence(limit) {
  if(limit < 1) return console.log('Limit must be greater than 0');

  for(var i = 0; i < limit; i++ ) {
    console.log( fibonacci(i) );
  }
}
```
