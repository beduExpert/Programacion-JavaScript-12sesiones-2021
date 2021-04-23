[`Programación con JavaScript`](../../Readme.md) > [`Sesión 08`](../Readme.md) > `Reto 01`

---

## Reto 1: Inflar un globo

### Objetivos

Crear event handlers y usar el event object para determinar las teclas presionadas.

#### Requisitos

Partir del siguiente documento HTML:

```html
<html>
  <head>
    <meta charset="utf8" />
    <title>Reto 1: Inflar un globo</title>
  </head>
  <body>

    <p>🎈</p>

    <script>
      // Code goes here
    </script>
  </body>
</html>
```

#### Desarrollo

En este reto el globo (🎈) debe inflarse (aumentar su tamaño) un 10% al presionar la flecha hacia arriba y desinflarse (disminuir su tamaño) un 10% el presionar la flecha hacia abajo.

Los emojis son considerados como texto por lo que puedes controlar el tamaño con la propiedad de CSS `font-size`. El valor inicial debe ser de `20px`.

Los nombres de las teclas de flecha que necesitas son `ArrowUp` y `ArrowDown`. Con el método `preventDefault()` podemos evitar que la página haga un scroll al presionar estas teclas.

Por último, si el tamaño del globo es mayor a `80px` se debe reemplazar por el emoji 💥 y eliminar el event handler.

<details>
  <summary>Solución</summary>

```javascript
var p = document.querySelector("p");
var size;

function setSize(newSize) {
  size = newSize;
  p.style.fontSize = size + "px";
}

setSize(20);

function handleArrow(event) {
  if (event.key == "ArrowUp") {
    if (size > 80) {
      p.textContent = "💥";
      document.body.removeEventListener("keydown", handleArrow);
    } else {
      setSize(size * 1.1);
      event.preventDefault();
    }
  } else if (event.key == "ArrowDown") {
    setSize(size * 0.9);
    event.preventDefault();
  }
}

document.body.addEventListener("keydown", handleArrow);
```

</details>
