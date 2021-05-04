[`Programación con JavaScript`](../../Readme.md) > [`Sesión 07`](../Readme.md) > `Reto 01`

---

## Reto 1: Reemplazar imágenes

### Objetivos

Manipular el DOM creando nuevos nodos y reemplazándolos con existentes.

#### Requisitos

Partir del siguiente documento HTML:

```html
<html>
  <head>
    <meta charset="utf8" />
    <title>Reto 1: Reemplazar Imágenes</title>
  </head>
  <body>
    <h1>Images</h1>

    <img src="https://picsum.photos/200/300" alt="First Image"/>
    <img src="https://picsum.photos/200/300" alt="Second Image"/>
    <img src="https://picsum.photos/200/300" alt="Third Image"/>

    <script>
      // Code goes here
    </script>
  </body>
</html>
```

#### Desarrollo

Reemplazar todas las imágenes del documento (etiquetas `<img/>`) con el texto que contienen en el atributo `alt`.

<details>
  <summary>Solución</summary>

```javascript
var images = document.body.getElementsByTagName("img");
for (var i = images.length - 1; i >= 0; i--) {
  var image = images[i];
  if (image.alt) {
    var text = document.createTextNode(image.alt);
    image.parentNode.replaceChild(text, image);
  }
}
```

</details>
