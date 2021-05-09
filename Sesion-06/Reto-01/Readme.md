[`Programación con JavaScript`](../../Readme.md) > [`Sesión 06`](../Readme.md) > `Reto 01`

---

## Reto 1: Vectores

### Objetivos

Crear un constructor, agregar métodos al prototype e instanciar múltiples objetos a partir de dicho constructor.

#### Requisitos

`N/A`

#### Desarrollo

Crear un function constructor `Vec` el cual representa un vector en dos dimensiones. Recibe dos parámetros `x` y `y`,
ambos valores numéricos que deben ser las propiedades del objeto.

Agregar los siguientes métodos al `prototype` de `Vec`:

1. `plus`: Recibe otro vector como parámetro y retorna un nuevo vector con la suma de ambos vectores.

2. `minus`: Recibe otro vector como parámetro y retorna un nuevo vector con la diferencia de ambos vectores.

3. `length`: Retorna la longitud del vector, es decir, la distancia del punto _(x, y)_ desde el origen _(0, 0)_.

```javascript
const Vec = function(x, y) {
  // Code goes here...
}

const vec1 = new Vec(1, 2);
const vec2 = new Vec(2, 3);

console.log(vec1.plus(vec2)); // Vec { x: 3, y: 5 }
console.log(vec1.minus(vec2)); // Vec { x: -1, y: -1 }
console.log(vec1.length()); // 2.23606797749979
```

> Para calcular la distancia desde (0, 0) hasta (x, y) se puede usar el teorema de Pitágoras: √(x2 + y2). 
> En JavaScript existe el método `Math.sqrt` para calcular raíces cuadradas.
