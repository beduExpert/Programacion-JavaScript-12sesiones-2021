[`Programación con JavaScript`](../../Readme.md) > [`Sesión 05`](../Readme.md) > `Reto 02`

---

## Reto 2: Group

### Objetivos

Crear un constructor, agregar métodos al prototype e instanciar múltiples objetos a partir de dicho constructor.

#### Requisitos

Haber terminado el [Reto 1](../Reto-01/Readme.md).

#### Desarrollo

Crear un function constructor `Group` el cual crea una lista (arreglo) vacía.

Agregar los siguientes métodos a `Group`:

1. `add`: Agrega un nuevo valor al grupo sólo si no existe.

2. `has`: Retorna un booleano indicando si el valor es un miembro del grupo.

3. `from`: Método estático que recibe un arreglo y crea un grupo con todos los elementos de dicho arreglo.

```javascript
var Group = function() {
  ...
}

var group = Group.from([1, 2, 3, 4, 5]);
console.log(group); // Group { members: [ 1, 2, 3, 4, 5 ] }
console.log(group.has(5)); // true
console.log(group.has(10)); // false

group.add(10);
console.log(group.has(10)); // true
```

<details>
  <summary>Solución</summary>

```javascript
var Group = function() {
  this.members = [];
}

Group.prototype.add = function(value) {
  if (!this.has(value)) {
    this.members.push(value);
  }
}

Group.prototype.has = function(value) {
  return this.members.includes(value);
}

Group.from = function(collection) {
  var group = new Group();

  for(var i = 0; i < collection.length; i++) {
    group.add(collection[i]);
  }
  return group;
}
```

</details>
