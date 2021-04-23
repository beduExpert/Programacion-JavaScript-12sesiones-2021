[`Programación con JavaScript`](../../Readme.md) > [`Sesión 01`](../Readme.md) > `Reto 01`

---

## Reto 1: Precedencia de operadores

### Objetivo

Practicar el orden de precedencia de los operadores en JavaScript.

#### Requisitos

Puedes hacer el siguiente ejemplo directo en la consola de Chrome.

#### Desarrollo

Intenta calcular el resultado de las siguientes operaciones antes de ver el resultado en la consola.

```javascript
var a = 5;
var b = 10;
var c = 15;

(3 + b) * c / a * 2;

((a + b * c) / 5) * 2;

b / a + 2 * c;

(a + b + c / c) * a;

((3 * a) / c) + a + b + c;  

a - (b + c) * a / 1;
```

Puedes consultar la tabla de precedencia si no estás seguro de qué operación hacer primero.

<details>
  <summary>Solución</summary>

```javascript
(3 + b) * c / a * 2; // 78

((a + b * c) / 5) * 2; // 62

b / a + 2 * c; // 32

(a + b + c / c) * a; // 80

((3 * a) / c) + a + b + c; // 31  

a - (b + c) * a / 1; // -120
```
</details>
