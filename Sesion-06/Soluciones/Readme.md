[`Programación con JavaScript`](../../Readme.md) > [`Sesión 06`](../Readme.md) > `Soluciones`

---

## Reto 1: Vectores

```javascript
const Vec = function(x, y) {
  this.x = x;
  this.y = y;
}

Vec.prototype.plus = function(other) {
  return new Vec(this.x + other.x, this.y + other.y);
}

Vec.prototype.minus = function(other) {
  return new Vec(this.x - other.x, this.y - other.y);
}

Vec.prototype.length = function() {
  return Math.sqrt(this.x * this.x + this.y * this.y);
}
```

---

## Reto 2: Group

```javascript
const Group = function() {
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
  const group = new Group();

  for(let i = 0; i < collection.length; i++) {
    group.add(collection[i]);
  }
  return group;
}
```

---

## Reto 3: Perímetro

```javascript
const Triangle = function(a, b, c) {
  this.a = a;
  this.b = b;
  this.c = c;
}

Triangle.prototype.getPerimeter = function() {
  return this.a + this.b + this.c;
}
```
