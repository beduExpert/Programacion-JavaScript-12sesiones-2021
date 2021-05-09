[`Programación con JavaScript`](../../Readme.md) > [`Sesión 05`](../Readme.md) > `Reto 03`

---

## Reto 3: Perímetro

### Objetivos

Crear un constructor, agregar métodos al prototype e instanciar múltiples objetos a partir de dicho constructor.

#### Requisitos

Haber terminado el [Reto 2](../Reto-02/Readme.md).

#### Desarrollo

Crear un function constructor `Triangle` con tres parámetros `a`, `b` y `c`. Cada uno representa un lado del triángulo.

Agregar el método `getPerimeter` al `prototype` de `Triangle`, el cual retorna el perímetro del triángulo.

```javascript
const Triangle = function(a, b, c) {
  // Code goes here...
}

const triangle = new Triangle(1, 2, 3);

console.log(triangle); // Triangle { a: 1, b: 2, c: 3 }
console.log(triangle.getPerimeter()); // 6
```
