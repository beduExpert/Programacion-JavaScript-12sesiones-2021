[`Programación con JavaScript`](../../Readme.md) > [`Sesión 05`](../Readme.md) > `Reto 03`

---

## Reto 3: Perímetro

### Objetivos

Crear un constructor, agregar métodos al prototype e instanciar múltiples objetos a partir de dicho constructor.

#### Requisitos

Haber terminado el [Reto 2](../Reto-02/Readme.md).

#### Desarrollo

Crear un function constructor `Triangle` con tres parámetros `a`, `b` y `c`. Cada uno representa una lado del triángulo.

Agregar el método `getPerimeter` al `prototype` de `Triangle`, el cual retorna el perímetro del tríangulo.

```javascript
var Triangle = function(a, b, c) {
  ...
}

var triangle = new Triangle(1, 2, 3);

console.log(triangle); // Triangle { a: 1, b: 2, c: 3 }
console.log(triangle.getPerimeter()); // 6
```

<details>
  <summary>Solución</summary>

```javascript
var Triangle = function(a, b, c) {
  this.a = a;
  this.b = b;
  this.c = c;
}

Triangle.prototype.getPerimeter = function() {
  return this.a + this.b + this.c;
}
```

</details>
