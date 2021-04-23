
[`Programación con JavaScript`](../Readme.md) > `Sesión 08`

# Sesión 8: Manipulación del DOM

## Objetivos

Generar scripts que permitan la manipulación e interacción con la web.

---

## Tabla de Contenidos

- **[Event handlers](#event-handlers)**

- **[Eventos y nodos del DOM](#eventos-y-nodos-del-dom)**

	- [Ejemplo 1: Eventos en nodos del DOM](./Ejemplo-01)

- **[Event object](#event-object)**

	- [Ejemplo 2: Usando event object](./Ejemplo-02)

- **[Tipos de eventos](#tipos-de-eventos)**

	- [Ejemplo 3: Key events](./Ejemplo-03)

	- [Reto 1: Inflar un globo](./Reto-01)

	- [Reto 2: Modal](./Reto-02)

	- [Reto 3: Navegando entre tabs](./Reto-03)

---

## Event handlers

Manipular el DOM creando nodos y modificando sus atributos carece de sentido si el usuario no tiene la posibildad de interactuar con nuestra aplicación o sitio web. El usuario en algún momento va a presionar una tecla, hacer click en un botón, o ingresar un valor en un input y espera que la interfaz reaccione de alguna forma en el momento que se realiza cualquiera de esas acciones.

Los navegadores son capaces de notificar o avisar a nuestro código cuando un evento sucede. En este contexto un evento es cuando el usuario o el navegador mismo manipula la página. Cuando el usuario hace click en un botón, cuando la página carga, o incluso cuando una ventana se cierra son ejemplos de eventos. El navegador nos permite registrar funciones conocidas como _handlers_ que se ejecutan cuando un evento en específico sucede.

```javascript
window.addEventListener("click", function() {
  console.log("Hello World!");
});
```

`window` es un objeto que representa la ventana del navegador donde se carga `document`. Al llamar el método `addEventListener` se registra el segundo argumento para ser llamado cuando el evento descrito en el primer argumento sucede. Como resultado, al hacer click (evento) en cualquier parte de la ventana se mostrará en consola un mensaje `Hello World!` (handler).

---

## Eventos y nodos del DOM

Todos los event handlers son registrados en un contexto. En el ejemplo anterior llamamos `addEventListener` en el objeto `window` por lo que el handler se registra para toda la ventana. Los elementos del DOM también cuentan con este método.

```html
<p>No handler here.</p>

<button>Click me</button>

<p>No handler here.</p>

<script>
  var button = document.querySelector("button");

  button.addEventListener("click", () => {
    console.log("Button clicked.");
  });
</script>
```

> El método `querySelector` retorna el primer elemento del DOM que hace match con el selector de CSS especificado.

Este handler está vinculado al elemento `button`. Lo clicks en el botón ejecutarán la función handler pero los clicks en los párrafos (o cualquier parte del documento) no.

Usar el atributo `onclick` tiene el mismo efecto, sin embargo, los nodos sólo pueden tener un atributo `onclick` por lo que sólo se puede registrar un handler de esta manera. Usando el método `addEventListener` se pueden registrar múltiples handlers sobre un mismo nodo.

También podemos eliminar handlers que hayamos creado con anterioridad usando el método `removeEventListener`.

```html
<button>Click me</button>

<script>
  var button = document.querySelector("button");

  function once() {
    console.log("Click once");
    button.removeEventListener("click", once);
  }

  button.addEventListener("click", once);
</script>
```

La función que le pasemos a `removeEventListener` debe ser la misma que se le dió a `addEventListener`. En este caso se debe definir una función y darle un nombre, de esta forma podemos pasar la funicón a ambos métodos.

#### [Ejemplo 1: Eventos en nodos del DOM](./Ejemplo-01)

---

## Event object

La función de un event handler recibe un argumento `event`. Este es un objeto con toda la información referente al evento. Por ejemplo, si quisiéramos saber cuál botón del mouse fue presionado podemos leer la propiedad `button` del event object.

```html
<button>Click Here</button>

<script>
  var button = document.querySelector("button");

  button.addEventListener("mousedown", function(event) {
    if (event.button == 0) {
      console.log("Left button");
    } else if (event.button == 1) {
      console.log("Middle button");
    } else if (event.button == 2) {
      console.log("Right button");
    }
  });
</script>
```

La información contenida en el event object puede variar dependiendo del tipo de evento.

#### [Ejemplo 2: Usando event object](./Ejemplo-02)

---

## Tipos de eventos

### Teclado

Cada vez que se presiona una tecla el navegador lanza un evento `keydown`, al soltar la tecla se ejecuta un evento `keyup`. Cuando usemos `keydown` hay que tomar en cuenta que no es un evento que se ejecute una sola vez, si la tecla se mantiene presionada el evento se seguirá ejecutando de manera constante.

Podemos determinar la tecla presionada con la propiedad `key` del event object. Esta propiedad contiene un string con el nombre de la tecla presionada. Adicionalmente, si queremos determinar una combinación de teclas el event object cuenta con las propiedades `shiftKey`, `ctrlKey`, `altKey` y `metaKey` que contienen un booleano indicando si la tecla `Shift`, `Control`, `Alt` o `Meta` respectivamente se encontraba presionada cuando el evento ocurrió.

> `Meta`: En teclados Macintosh es la tecla comando (⌘). En teclados Windows es la tecla window (⊞).

### Mouse

Similar a los eventos `keydown` y `keyup`, cuando presionamos un botón del mouse se ejcuta el evento `mousedown` y `mouseup` cuando se suelta el botón. Esto sucede en el nodo del DOM  donde se encuentre el cursor al momento que ocurre el evento. Después del evento `mouseup` se ejecuta el evento `click` que ya hemos visto anteriormente. En caso de que sucedan dos clicks de manera continua se lanza el evento `dblclick`.

#### [Ejemplo 3: Key events](./Ejemplo-03)

> Consultar la [siguiente documentación](https://developer.mozilla.org/es/docs/Web/Events) para una lista completa de los tipos de eventos.

#### [Reto 1: Inflar un globo](./Reto-01)

#### [Reto 2: Modal](./Reto-02)

#### [Reto 3: Navegando entre tabs](./Reto-03)
