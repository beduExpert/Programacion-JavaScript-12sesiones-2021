[`Programación con JavaScript`](../../Readme.md) > [`Sesión 07`](../Readme.md) > `Soluciones`

---

## Reto 1: Flatten

```javascript
function flatten(arrays) {
  return arrays.reduce(function(flat, current) {
    return flat.concat(current);
  }, []);
}
```

---

## Reto 2: Compact

```javascript
function compact(array) {
  return array.filter(function(element) {
    return !!element;
  });
}
```

---

## Reto 3: Loop

```javascript
function loop(start, test, update, body) {
  for (let value = start; test(value); value = update(value)) {
    body(value);
  }
}
```
