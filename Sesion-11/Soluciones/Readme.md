[`Programación con JavaScript`](../../Readme.md) > [`Sesión 11`](../Readme.md) > `Soluciones`

---

## Reto 1: Creando Promise.all

```javascript
function promiseAll(promises) {
  return new Promise((resolve, reject) => {
    let results = [];
    let pending = promises.length;
    for (let i = 0; i < promises.length; i++) {
      promises[i].then(result => {
        results[i] = result;
        pending--;
        if (pending === 0) resolve(results);
      }).catch(reject);
    }
    if (promises.length === 0) resolve(results);
  })
}
```

---

## Reto 2: Llamar función async

```javascript
async function wait() {
  await new Promise(resolve => setTimeout(resolve, 1000));

  return 'Hello World';
}

function log() {
  wait().then(result => console.log(result));
}

log()
```

---

## Reto 3: Asynchronous Output

```javascript
const processAction = (i, callback) => {
  setTimeout(function() {
    callback("Processed Action " + i);
  }, Math.random()*1000);
}

const triggerActions = (count) => {
  const promises = [];
  const generatePromise = (i) => {
    return new Promise((resolve) => {
      processAction(i, resolve);
    });
  }
  for (let i = 1; i <= count; i += 1) {
    promises.push(generatePromise(i));
  }
  Promise.all(promises)
    .then((strings) =>
      strings.forEach((string) => console.log(string)));
}

triggerActions(10);
```
