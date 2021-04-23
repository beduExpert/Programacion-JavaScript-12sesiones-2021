[`Programación con JavaScript`](../../Readme.md) > [`Sesión 08`](../Readme.md) > `Ejemplo 03`

---

## Ejemplo 3: Key events

### Objetivo

Determinar las teclas presionadas al disparar un evento.

#### Requisitos

En una nueva carpeta vamos a crear un archivo `HTML` en blanco llamado `index.html`:

```html
<html>
  <head>
    <title>Ejemplo 3: Key events</title>
  </head>
  <body>

    <h2>Press Enter to turn this page blue.</h2>
    <h2>Press Ctrl + Enter to turn this page orange.</h2>

    <script>
      // Code goes here
    </script>
  </body>
</html>
```

Opcionalmente se puede manejar el código de JavaScript en un archivo independiente como se ha trabajado en sesiones anteriores.

#### Desarrollo

En este ejemplo vamos a ver cómo realizar un cambio en el DOM al presionar una tecla o combinación de teclas. Agregaremos un event handler a la global `window` de tipo `keydown` que se ejecuta al presionar una tecla.

```javascript
window.addEventListener("keydown", function(event) {
  if (event.key == "Enter") {
    document.body.style.background = "lightblue";
  }

  if (event.key == "Enter" && event.ctrlKey) {
    document.body.style.background = "orange";
  }
});
```

Estamos leyendo dos propiedades del event object, la primera es `key` que nos dice qué tecla fue presionada. La segunda propiedad que nos interesa es `ctrlKey` que nos ayuda a determinar si la tecla `ctrl` estuvo presionada cuando se lanzó el evento. Vamos a cambiar el color de fondo del documento, si se presiona solamente la tecla `Enter` el color será azul, pero si se presiona la combinación de teclas `Ctrl + Enter` entonces el color será naraja.

```javascript
window.addEventListener("keyup", function(event) {
  if (event.key == "Enter") {
    document.body.style.background = "";
  }
});
```

Por último, necesitamos regresar al color por default cuando las teclas fueron soltadas, para eso utilizamos el evento `keyup` y verificamos que la tecla que se soltó es la misma que cambia el color, es decir, la tecla `Enter`.

![Pressing Keys](./assets/pressing-keys.gif)
