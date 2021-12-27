# Vue Sintaxis

## Directivas

```html
<!DOCTYPE html>
<html lang="es">
  <head>
    <meta charset="UTF-8" />
    <title>Vue 3 CDN</title>
  </head>
  <body>
    <div id="app">
      <h1>{{ saludo }}</h1>
    </div>
    <script src="https://unpkg.com/vue@next"></script>
    <script>
      const App = {
        data() {
          return {
            saludo: "Hola Mundo",
          };
        },
      };
      Vue.createApp(App).mount("#app");
    </script>
  </body>
</html>
```
### MUSTACHE o llaves dobles - enlazar datos al documento html

Vue.js [mustache](https://v3.vuejs.org/guide/template-syntax.html#interpolations)

#### template
```html
<h1>{{ saludo }}</h1>
<h1>{{ saludo.toLocaleUpperCase() }}</h1>
```

#### script data()
```js
saludo: 'Hola Mundo',
```
        
### V-MODEL - añadir datos desde el documento html

Vue.js [v-model](https://es.vuejs.org/v2/guide/components.html#Usando-v-model-en-Componentes)
#### template
```html
<input type="text" v-model="nombre" >
 <h1>{{ nombre }}</h1>

```

#### script data()
```js
nombre: '',
```
### V-BIND / : - enlazar con atributos de las etiquetas html

Vue.js [v-bind](https://es.vuejs.org/v2/guide/syntax.html)

```html
<!-- full syntax -->
<a v-bind:href="url"> Google </a>

<!-- abreviado -->
<a :href="url"> Google </a>
<img :src="imagen">
```
#### script data()
```js
url: 'https://www.google.es',
imagen: './imagenes/logo.png',
```
### V-ON / @CLICK - escuchar/ejecutar funciones en el documento html

Vue.js [@click](https://es.vuejs.org/v2/guide/syntax.html)

```html
<!-- full syntax -->
<button v-on:click="saludar"> Saludo </button>
<!-- abreviado -->
<button @click="saludar"> Saludo </button>
```
#### script methods:
```js
methods: {
  saludar() {
  alert('Bienvenidos')
  console.log('Bienvenidos')
  }
}
```

### V-FOR - iteración de arrays (matrices) de objetos

Vue.js [v-for](https://es.vuejs.org/v2/guide/list.html#Mapeando-una-matriz-a-elementos-con-v-for)

```html
<div v-for="(objeto, index) in objetos" :key="index">
  {{ index }}: {{ objeto.nombre }}
</div>
```
#### script data()
```js
objetos: [
  { nombre: 'Objeto1' },
  { nombre: 'Objeto2' }
]
```
### V-IF / v-show - condicionales

Vue.js [v-if](https://es.vuejs.org/v2/guide/conditional.html#v-if)

Aquí veremos como mostrar/ocultar un botón en función de una variable booleana

```html
<button v-show="this.editar === true" 
    @click.prevent="actualizarProducto(producto)" 
    class="btn btn-primary">Editar
</button>
<button v-show="this.editar === false" 
    @click.prevent="agregarProducto(producto)" 
    class="btn btn-primary">Guardar
</button>
```
### Como modificar una variable booleana

Con ***this.editar = !this.editar*** invertimos el booleano.

```html
 <button @click.prevent="
  this.editar = !this.editar;" 
  class="btn btn-primary">Editar/Guardar
</button>
```
```js
  editar: false,

```
## Final
```html
<!DOCTYPE html>
<html lang="es">
  <head>
    <meta charset="UTF-8" />
    <title>Vue 3 CDN</title>
  </head>
  <body>
    <div id="app">
      <h1>{{ saludo }}</h1>
      <h1>{{ saludo.toLocaleUpperCase() }}</h1>
      <input type="text" v-model="nombre" />
      <h1>{{ nombre }}</h1>

      <!-- full syntax -->
      <a v-bind:href="url"> Google </a>

      <!-- abreviado -->
      <a :href="url"> Google </a>
      <img :src="imagen" />

      <!-- full syntax -->
      <button v-on:click="saludar">Saludo</button>
      <!-- abreviado -->
      <button @click="saludar">Saludo</button>

      <div v-for="(objeto, index) in objetos" :key="index">
        {{ index }}: {{ objeto.nombre }}
      </div>
      <button
        v-show="this.editar === true"
        @click.prevent="actualizarProducto(producto)"
        class="btn btn-primary"
      >
        Editar
      </button>
      <button
        v-show="this.editar === false"
        @click.prevent="agregarProducto(producto)"
        class="btn btn-primary"
      >
        Guardar
      </button>

      <button
        @click.prevent="
          this.editar = !this.editar;"
        class="btn btn-primary"
      >
        Editar/Guardar
      </button>
    </div>
    <script src="https://unpkg.com/vue@next"></script>
    <script>
      const App = {
        data() {
          return {
            saludo: "Hola Mundo",
            nombre: "",
            url: "https://www.google.es",
            imagen: "./imagenes/StarLord.jpeg",
            editar: true,
            objetos: [{ nombre: "Objeto1" }, { nombre: "Objeto2" }],
          };
        },
        methods: {
          saludar() {
            alert("Bienvenidos");
            console.log("Bienvenidos");
          },
        },
      };
      Vue.createApp(App).mount("#app");
    </script>
  </body>
</html>
```
