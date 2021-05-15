[`Programación con JavaScript`](../../Readme.md) > [`Sesión 08`](../Readme.md) > `Soluciones`

---

## Reto 1: Webpack y CSS

Estructura de archivos:

```
demo
|- /src
    |- index.html
    |- js
      |- index.js
    |- css
      |- styles.css
```

Instalar loaders

```text
npm install --save-dev css-loader style-loader
```

- **css-loader:** le permite a webpack recolectar todos los estilos que encuentre y colocarlos en un string.
- **style-loader:** inyecta los estilos generados por `css-loader` en el DOM.

`webpack.config.js`

```javascript
const path = require('path');
const HtmlWebpackPlugin = require('html-webpack-plugin');

module.exports = {
  entry: './src/js/index.js',
  output: {
    path: path.resolve(__dirname, 'dist'),
    filename: 'bundle.js'
  },
  plugins: [
    new HtmlWebpackPlugin({
      filename: 'index.html',
      template: './src/index.html'
    })
  ],
  module: {
    rules: [
      { test: /\.css$/, use: ['style-loader', 'css-loader'] },
    ]
  },
  devServer: {
    contentBase: path.resolve(__dirname, 'dist')
  }
}
```

`styles.css`

```css
h1 {
  text-align: center;
}
```

`index.js`

```javascript
import '../css/styles.css'
```

---

## Reto 2: 

---

## Reto 3: 
