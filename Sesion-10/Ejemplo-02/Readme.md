[`Programación con JavaScript`](../../Readme.md) > [`Sesión 08`](../Readme.md) > `Ejemplo 02`

---

## Ejemplo 2: Usando event object

### Objetivo

Implementar propiedades del event object para manipular el DOM.

#### Requisitos

En una nueva carpeta vamos a crear un archivo `HTML` en blanco llamado `index.html`:

```html
<html>
  <head>
    <title>Ejemplo 2: Usando event object</title>
  </head>
  <body>
    <h1 id="title">Hello World!</h1>

    <input type="text" id="text" />

    <script>
      // Code goes here
    </script>
  </body>
</html>
```

Opcionalmente se puede manejar el código de JavaScript en un archivo independiente como se ha trabajado en sesiones anteriores.

#### Desarrollo

En el ejemplo anterior vimos como cambiar las propiedad de un nodo a través de event handlers. En este ejemplo vamos a usar la información contenida en el event object para manipular el DOM.

```javascript
var title = document.getElementById('title');

var input = document.getElementById('text');
```

Ahora usaremos el método `addEventListener` para registrar un handler en el `<input/>`, el evento que queremos escuchar es `input`, el cual se dispara cuando hay un cambio en el nodo.

```javascript
input.addEventListener("input", function(event) {
  title.textContent = event.target.value;
});
```

La propiedad `textContent` nos permite obtener o cambiar el contenido de texto de un nodo. La propiedad `target` del event object es una referencia al nodo que lanzó el evento, en este caso nuestro `<input/>`, por lo que podemos acceder al atributo `value` de ese elemento.

![Changing Text](./assets/changing-text.gif)
