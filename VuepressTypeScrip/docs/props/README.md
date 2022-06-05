---
sidebar: auto
---

# Comenzando

## Tipos en las Props

### Props

#### Componente Contador

Con **defineProps** + **<{ }>** estamos utilizando **typescript**,**defineProps** es un tipo de función de vue.js **macros del compilador** que solo se pueden usar dentro de **< script setup >**

Contador.vue

```vue
<script setup lang="ts">
import { ref } from "vue";

const props = withDefaults(
  defineProps<{
    limite: number;
    alertaLimiteMensajes?: string;
  }>(),
  {
    alertaLimiteMensajes: "No puede ser mas alto",
  }
);

const contador = ref<number | string>(0);

function incrementar(num: number) {
  if (typeof contador.value === "number") {
    if (contador.value >= props.limite) {
      alert(props.alertaLimiteMensajes);
    } else {
      contador.value += num;
    }
  }
}
</script>

<template>
  <div>
    <p>{{ contador }}</p>
    <button @click="incrementar(2)">Incrementar</button>
  </div>
</template>
```
#### Views HomeView

HomeView.vue

```vue
<template>
  <h1>{{ infoApp.nombre }}</h1>
  <h1>{{ infoApp.texto }}</h1>
  <Contador
    :limite="10"
    :alerta-limite-mensajes='"No puede superar"'
  />
</template>
```