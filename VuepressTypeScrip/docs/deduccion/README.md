---
sidebar: auto
---
# Comenzando

## Tipos de datos por Deducción

### Ref

En este caso al crear una **const** con un valor númerico observamos, si acercamos el cursor al nombre, que de forma autómatica esta asigna el tipo de dato **number**

```vue
<script setup lang="ts">
import { ref } from 'vue'
import { contadorStore } from '../stores/contador'

const contar = contadorStore()

// Deduce que es de tipo Ref<number>
var contador = ref(0);

function incrementar() {
  contador.value ++
  }
</script>

<template>
    <button @click="incrementar">Incrementar</button>
   <p>{{ contador }}</p>
</template>
```
### Reactive

En este caso al crear una **const** con valores de cadena de texto, observamos, si acercamos el cursor al nombre, que de forma autómatica esta asigna el tipo de dato **string**

#### script

```js
import { ref, reactive } from 'vue'

const infoApp = reactive({
  nombre: 'Contador',
  texto: 'Vamos a contar'
})
```

#### template

```vue
<template>
  <h1>{{ infoApp.nombre }}</h1>
  <h1>{{ infoApp.texto }}</h1>
  <p>{{ contador }}</p>
  <button @click="incrementar">Incrementar</button>
</template>
```


