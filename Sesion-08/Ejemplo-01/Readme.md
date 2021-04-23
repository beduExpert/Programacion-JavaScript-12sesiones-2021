[`Programación con JavaScript`](../../Readme.md) > [`Sesión 08`](../Readme.md) > `Ejemplo 01`

---

## Ejemplo 1: Eventos en nodos del DOM

### Objetivo

Agregar event handlers a distintos nodos.

#### Requisitos

En una nueva carpeta vamos a crear un archivo `HTML` en blanco llamado `index.html`:

```html
<html>
  <head>
    <title>Ejemplo 1: Eventos en nodos del DOM</title>
  </head>
  <body>
    <h1 id="title">Hello World</h1>

    <button id="red">Red</button>
    <button id="blue">Blue</button>
    <button id="black">Black</button>

    <script>
      // Code goes here
    </script>
  </body>
</html>
```

Opcionalmente se puede manejar el código de JavaScript en un archivo independiente como se ha trabajado en sesiones anteriores.

#### Desarrollo

En este ejemplo vamos a cambiar el color del título agregando event handlers a todos los botones del documento. Tanto el título como los botones cuentan con un id único por lo que podemos usar `getElementById`.

```javascript
var title = document.getElementById('title');

var redButton = document.getElementById('red');

var blueButton = document.getElementById('blue');

var blackButton = document.getElementById('black');
```

Ahora usaremos el método `addEventListener` para registrar un handler a cada botón. El cambio de color lo haremos asignando la propiedad `style` del nodo `title`.

```javascript
redButton.addEventListener("click", function() {
  title.style = "color: red;";
});

blueButton.addEventListener("click", function() {
  title.style = "color: blue;";
});

blackButton.addEventListener("click", function() {
  title.style = "color: black;";
});
```

![Ejemplo 1](./assets/colors.gif)
