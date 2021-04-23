[`Programación con JavaScript`](../Readme.md) > `Sesión 01`

---

# Sesión 1: Fundamentos de JS

## Objetivos

Analizar la trayectoria de JavaScript, evaluar por qué es una buena opción aprenderlo y usar sus fundamentos.

---

## Tabla de Contenidos

- **[¿Por qué Javascript?](#por-qué-javascript)**

- **[¿Cómo comenzar y qué hacer?](#cómo-comenzar-y-qué-hacer)**

- **[¿Qué es Javascript?](#qué-es-javascript)**

- **[Tu primer archivo Javascript](#tu-primer-archivo-javascript)**

- **[¿Qué son las variables?](#qué-son-las-variables)**

- **[Tipos de Datos](#tipos-de-datos)**

- **[Operador typeof](#operador-typeof)**

  - [Ejemplo 1: Tipos de datos y operador `typeof`](./Ejemplo-01)

- **[Type coercion](#type-coercion)**

- **[Operadores](#operadores-básicos)**

  - [Ejemplo 2: Operadores](./Ejemplo-02)

- **[Precedencia de operadores](#precedencia-de-operadores)**

  - [Ejemplo 3: Precedencia de operadores](./Ejemplo-03)

  - [Reto 1: Precedencia de operadores](./Reto-01)

---

## ¿Por qué Javascript?

Te damos la gran bienvenida a Javascript.

Javascript hoy es uno de los lenguajes de programación más usados en el mundo.

En la última encuesta de 2019, realizada a la plataforma [Stack Overflow](https://stackoverflow.com/), foro más importante de desarrolladores en el mundo, se comprobó que Javascript es y seguirá teniendo mucha tracción en los siguientes años.

**No es el único que seguirá creciendo**, claro está, pero el impacto de este se ha mantenido y progresa anualmente.

> Te recomendamos leer la investigación completa [sobre el ecosistema tecnológico aquí](https://insights.stackoverflow.com/survey/2019).

![Survey 2019](https://i.imgur.com/ZZmILsS.png)

---

Atentos de estas tendencias, muchas empresas confían sus productos digitales a Javascript, parcial o totalmente, en diferentes áreas de desarrollo.

Notemos que es posible, con Javascript, trabajar aplicaciones móviles y escritorio.

![tendencias](https://i.imgur.com/nlzlvO0.png)

---

Ahora, el conjunto de tecnologías que necesitarás para construir aplicaciones web puede ser este (importante destacar que no es el único pero es de los más robustos):

![](https://i.imgur.com/UgG62hG.png)

Observa que:

- Del lado del cliente tenemos React, un framework **basado en Javascript** que te permite organizar, mantener y gestionar una aplicación basado en un concepto llamado componentes.

> Destacar que React cuenta con un soporte sólido por parte de la comunidad de desarrolladores y también de Facebook, como compañía. De ahí su seguridad y confianza.

- En el lado del servidor tenemos Node.js, el cual es un ambiente de desarrollo que permite el uso de Javascript del lado del servidor. Este te permitirá conectar con el cliente y con la base de datos, siendo un escudo de seguridad para ambas partes.

- Finalmente, encontramos MongoDB, una base de datos no relacional, el cual es muy amigable y al trabajar con él para su manejo, verás que se parecerá mucho al lenguaje de Javascript.

## ¿Cómo comenzar y qué hacer?

Para poder utilizar todas las tecnologías mencionadas y crear aplicaciones robustas, deberás formar buenas bases en Javascript.

A pesar de que es un lenguaje el cual podrás aplicar en poco tiempo, practicar es la clave.

Te compartimos consejos para mantenerte enfocado y persistente:

- Al inicio, probablemente muchos conceptos no tengan mucho sentido o implique mucho trabajo comprenderlos. **Es normal.** Sólo es cuestión de ejercitar lógica con muchos ejercicios y retos, los cuales la gran mayoría te los iremos compartiendo a lo largo del módulo.

- No tengas miedo en pedir ayuda o asumir que no sabes. Las personas que se dedican o implican tecnología en sus carreras profesionales saben que para crecer más rápido deben de aceptar que no lo saben todo. **Acercarse a otras personas alrededor cuando hay obstáculos hará más fácil tu progreso.**

- Encuentra espacios de estudio. Programar puede parecer diferente a otra área profesional debido a que necesitas momentos donde debes compartir, debatir y hablar sobre tus conclusiones técnicas, pero también te servirá mucho encontrar lugares, tiempos, momentos, donde puedas concentrarte, enfocarte y teclear mucho.

- Se vale Googlear. Probablemente llegues a estancarte y pasar una o dos horas en algunas líneas de código. Ten la confianza de ir a Google y buscar la respuesta. Encontrarás muchos desarrolladores que han pasado por ese mismo momento y han compartido cómo lo resolvieron. **Buscar ayuda en Internet es normal.**

> Cabe aclarar, "copiar y pegar" código **no es una buena práctica**. Es importante que todo el código que tú coloques en tu proyecto lo entiendas. Sepas por qué está ahí. Esto hará que tu aplicación pueda seguir creciendo y sigas teniendo, junto con tu equipo, el control del mismo.

Ahora si, comencemos.

---

## ¿Qué es Javascript?

Javascript (JS) es:

1. Un lenguaje de programación que permite ejecutarse principalmente en cada navegador (Google Chrome, Safari, Firefox, Opera, etc.).

2. Multiplataforma. Puede ser utilizado en muchas plataformas y sistemas. Podemos usarlo fuera del navegador a través de ciertos programas adicionales.

3. Multiparadigma. Se puede manejar orientación a objetos, funcional, reactivo. Más adelante explicaremos como se utilizan y para qué nos sirven.

4. **Diferente a JAVA. Son diferentes lenguajes. Javascript no es JAVA**

5. Un jugador que hace equipo, en el navegador, a lado de HTML y CSS, para que el usuario pueda usar la aplicación.

   1. HTML maneja el contenido, la estructura, el esqueleto, el "markup".
   2. CSS maneja la presentación, el diseño, la visualización de la aplicación.
   3. JS maneja la interactividad, efectos, dinamismo y más adelante, la gestión de datos y el flujo de los mismos a otras áreas de la aplicación.

![Variables](https://i.imgur.com/yNwZN3I.png)

---

## Tu primer archivo Javascript

- En tu computadora, crearás una carpeta llamada `bedu-sesion-1`. Aquí colocaremos todos nuestros ejercicios siguientes.

- Abrirás tu editor de preferencia y darás click en "Open Folder" en la parte posterior de la ventana. Buscarás la carpeta, la seleccionarás y la abrirás.

## ¿Qué son las variables?

Las variables se utilizan para almacenar información dentro de tu programa para ser manipulados.

En el modo más general, te ayudan a **etiquetar datos**. Los llamaremos en el momento que los necesitemos a lo largo del programa.

![Variables](https://i.imgur.com/toMeYM2.png)

Las variables se dividen en 4 partes:

```javascript
var deporte = "Atletismo";
```

- **Declaración (`var`)**. Cuando comienzas una variable, debes de utilizar la palabra `var`
- **Nombre (etiqueta)**. Irá del lado izquierdo. Será cómo llamarás la variable más adelante.
- **Asignación (`=`)**. A diferencia de la aritmética donde se le conoce como "igual", en Javascript se le conoce como asignación, el cual asignará el valor de lo que el área de su lado derecho genere hacia el lado izquierdo (Nombre).
- **Valor (Tipo de dato)**. Puede ser un texto, un número, un conjunto de datos (objetos, arreglos).

---

Ahora bien, nombrar tus variables implica que deberán ser lo más descriptivas posibles.

Es decir, que si otras personas leyeran tu código, entenderían rápidamente que significa cada dato porque el nombre de su variable lo explica todo. (Fig 1.1)

**`Fig. 1.1`**

```javascript
var saludo = "Hola Mundo";
var perro = "Firulais";
var pais = "México";
var edad = 35;
```

Si tú lees el nombre de las variables anteriores, rápidamente comprendes de qué tratan.

Si generas una variable que implica dos palabras, te recomendamos usar una técnica llamada **"Camel Case"**. (Fig 1.2)

Observemos un ejemplo:

**`Fig. 1.2`**

```javascript
var paisLatinoamericano = "México";
var animalVerde = "Rana";
var impuestosAnuales = 250000;
```

**"Camel Case"** implica:

- Conectar ambas palabras sin espacio, volviéndola una.
- La palabra comenzará con minúscula.
- La segunda palabra empezará con mayúscula.

Con esto claro, hablemos de los **tipos de datos**.

---

## Tipos de Datos

Todos los lenguajes de programación cuentan con estructuras de datos las cuales varían de un lenguaje a otro.
JavaScript es un lenguaje de tipado débil, significa que no es necesario declarar el tipo de variable antes de
usarla. El tipo de dato es determinado automáticamente cuando el programa esté siendo procesado.

JavaScript cuenta con seis tipos de datos que pueden ser divididos en tres categorías:

#### Primitivos

- String
- Number
- Boolean

#### Compuestos (Referencia)

- Object
- Array
- Function

#### Especiales

- Undefined
- Null

### String

Este tipo de dato es utilizado para almacenar cadenas de texto. Los strings son creados con comillas dobles o sencillas alrededor de uno o más caracteres.

```javascript
var a = 'Hello World!';	// Comillas sencillas
var b = "Hello World!";	// Comillas dobles
```

Las comillas también pueden formar parte de la cadena de texto siempre y cuando no coincidan con las comillas que abren y cierran el string.

```javascript
var a = "Let's learn JavaScript.";	// Comilla sencilla dentro de comillas dobles
var b = 'He said "Hello" and left.';	// Comillas dobles dentro de comillas sencillas
var c = 'We\'ll never stop learning.';	// Escapando comilla sencilla con backslash
```

### Number

El tipo de dato Number se usa para representar números enteros positivos o negativos con o sin punto decimal, incluso se puede usar en números con notación científica.

```javascript
var a = 12;	// Entero
var b = 32.43;	// Decimal
var c = 2.25e+6;	// Equivalente a 2.25x10^6 o 2250000
var d = 2.25e-6;	// Equivalente a 2.25x10-6 o 0.00000225
```

Este tipo de dato incluye algunos valores especiales: `Infinity`, `-Infinity` y `NaN`.

`Infinity` representa el infinito matemático `∞`, el cual es mayor a cualquier otro número. Se obtiene al dividir un número mayor o menor a cero entre cero.

```javascript
console.log(7 / 0);	// Infinity
console.log(-7 / 0);	// -Infinity
```

Por otro lado, `NaN` representa un valor no numérico. Es el resultado de una operación matemática inválida.

```javascript
console.log("Hello World" / 2);	// NaN
console.log("Hello World" * 2);	// NaN
console.log(Math.sqrt(-1)); // NaN
```

### Boolean

Las variables que contengan este tipo de dato sólo pueden almacenar uno de dos valores: `true` o `false`. Normalmente se usan para representar estados que signifiquen sí (`true`) o no (`false`), encendido (`true`) o apagado (`false`), etc.

```javascript
var isUserActive = true;	// Sí, el usuario se encuentra activo
var isUserAdmin = false;	// No, el usuario no es admin
```

### Undefined

Cuando una variable es declarada pero no se le ha asignado un valor, por default su valor es `undefined`.

```javascript
var a;
var b = 'Hello World';

console.log(a);	// undefined
console.log(b);	// Hello World
```

### Null

Este es otro tipo de dato especial con un único valor posible: `null`. Cuando encontremos `null` significa que no hay valor. No es lo mismo que cero o `undefined`, simplemente es `null` o nada.

Se puede vaciar una variable de manera explícita asignando el valor `null`.

```javascript
var a = 'Hello World';
console.log(a);	// Hello World

a = null
console.log(a);	// null
```

---

## Operador `typeof`

El operador `typeof` es utilizado para averiguar qué tipo de dato contiene una variable. Puede ser usado con o sin paréntesis (`typeof(a)` o `typeof a`).

#### [Ejemplo 1: Tipos de datos y operador `typeof`](./Ejemplo-01)

---

## Type coercion

La coerción de datos o type coercion es el proceso de convertir un valor de un tipo de dato a otro, por ejemplo, string a number, boolean a string, etc. Dicho proceso se puede dar de manera tanto explícita como implícita.

La forma explícita es cuando se quiere hacer de manera intencional usando las funciones adecuadas como `String(value)` o `Number(value)`, a esto también se le conoce como type casting.

Anteriormente mencionamos que JavaScript es un lenguaje de tipado débil, es por ello que los valores pueden cambiar de tipo de dato de manera automática, esto es la coerción de datos implícita. Usualmente pasa cuando aplicamos algún operador a valores con tipos de datos distintos.

En JavaScript sólo existen tres tipos de conversiones posibles:

- String
- Number
- Boolean

### String conversion

Para convertir un valor a string de manera explcícita usamos la función `String()`. La coercion implícita se da cuando usamor el operador `+` y cualquiera de los operandos es un string.

```javascript
String(123);	// Explícito
123 + '';	// Implícito
```

Todos los valores primitivos se pueden convertir en strings.

```javascript
String(123);	// '123'
String(3.14);	// '3.14'
String(true);	// 'true'
String(false);	// 'false'
String(undefined);	// 'undefined'
String(null);	// 'null'
```

### Numeric conversion

Para convertir explícitamente un valor a tipo numérico se aplica la función `Number()`. Le coerción implícita es un poco más compleja que la de strings porque se da en distintias formas, como el uso de operadores aritméticos, toma en cuenta que para el caso del operador `+` es string conversion y no numérico si uno de los operandos es string, como ya se mencionó anteriormente.

```javascript
Number('123');	// Explícito
+ '123';	// Implícito
1 - '1';	// Implícito
2 * '2';	// Implícito
```

Los valores primitivos también pueden ser convertidos a tipos numéricos con distintos resultados.

```javascript
Number(' 10 ');	// 12
Number('-10');	// 10
Number('123abc');	// NaN
Number(true);	// 1
Number(false);	// 0
Number(null);	// 0
Number(undefined);	// NaN
```

### Boolean conversion

Al igual que con strings y números, para una conversión explícita se usa una función, en este caso es `Boolean()`. La coerción implícita se da en un contexto lógico o al usar operadores lógicos.

```javascript
Boolean(1);	// Explícito
if(1) { ... }	// Implícito - Contexto lógico
!!2;	// Implícito - Operador lógico
2 || 'Hello World';	// Implícito - Operador lógico
```

> En la siguiente sesión se vará más a detalle los operadores lógicos y booleanos

---

## Operadores Básicos

Con respecto al tipo de datos `Number` puedes ejecutar operaciones para cambiar su valor.

| Operador | Descripción                       | Ejemplo Javascript    | Observaciones                                     |
|----------|-----------------------------------|-----------------------|---------------------------------------------------|
| +        | Adición                           | var resultado = 4 + 3 |                                                   |
| -        | Substracción                      | var resultado = 4 - 3 |                                                   |
| *        | Multiplicación                    | var resultado = 4 * 3 |                                                   |
| /        | División                          | var resultado = 4 / 2  | "resultado" devolvería 2                                              |
| %        | "Modulus"<br>Residuo de la división | var resultado = 4 % 2 | "resultado" devolvería 0                          |
| ++       | Incremento                        | var resultado = 4++   | "resultado" devolvería 5, <br> después de su ejecución |
| --       | Decremento                        | var resultado = 4--   | "resultado" devolvería 3, <br> después de su ejecución |

#### [Ejemplo 2: Operadores](./Ejemplo-02)

---

## Precedencia de Operadores

La precedencia es el orden en el cual los operadores se evaluan al momento de ejecutar la operación.

<table>
  <tr>
    <th>Precedencia</th>
    <th>Operador</th>
    <th>Descripción</th>
    <th>Asociatividad</th>
  </tr>
  <tr>
    <td>Primero</td>
    <td>(...)</td>
    <td>Agrupación</td>
    <td>n/a</td>
  </tr>
  <tr>
    <td rowspan="2">Segundo</td>
    <td>++</td>
    <td>Incremento</td>
    <td>n/a</td>
  </tr>
  <tr>
    <td>--</td>
    <td>Decremento</td>
    <td>n/a</td>
  </tr>
  <tr>
    <td class="tg-0lax" rowspan="2">Tercero</td>
    <td class="tg-0lax">+</td>
    <td class="tg-0lax">Unario más</td>
    <td class="tg-0lax" rowspan="2">Deracha a izquierda</td>
  </tr>
  <tr>
    <td class="tg-0lax">-</td>
    <td class="tg-0lax">Negación unaria</td>
  </tr>
  <tr>
    <td rowspan="3">Cuarto</td>
    <td>\*</td>
    <td>Multiplicación</td>
    <td rowspan="3">Izquierda a derecha</td>
  </tr>
  <tr>
    <td>/</td>
    <td>División</td>
  </tr>
  <tr>
    <td>%</td>
    <td>Módulo</td>
  </tr>
  <tr>
    <td rowspan="2">Quinto</td>
    <td>+</td>
    <td>Adición</td>
    <td rowspan="2">Izquierda a derecha</td>
  </tr>
  <tr>
    <td>-</td>
    <td>Substracción</td>
  </tr>
</table>

#### [Ejemplo 3: Precedencia de operadores](./Ejemplo-03)

#### [Reto 1: Precedencia de operadores](./Reto-01)
