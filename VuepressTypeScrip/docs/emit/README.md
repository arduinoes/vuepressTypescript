---
sidebar: auto
---

# Comenzando

## Tipos en los Emit

### Emit Component > ControlBoton

Con **defineEmits** + **<{ }>** estamos utilizando **typescript**,**defineEmits** es un tipo de función de vue.js **macros del compilador** que solo se pueden usar dentro de **< script setup >**. Observa que el evento tiene dos parámetros, el **nombre** y el **payload** y no devuelve nada **: void**

**ControlBoton.vue**

```vue
<script setup lang="ts">

const emit = defineEmits<{
    // nombre del evento, Payload dato
    (event: 'incrementar', num: number): void;
    (event: 'reiniciarContador'): void;
}>()

</script>

<template>
 <button @click="emit('incrementar', 2)">Incrementar</button>
 <button @click="emit('reiniciarContador')">Reiniciar contador</button>
</template>
```

Component > Contador.vue

script

```js
import ControlBoton from '../components/ControlBoton.vue'
```

template

```vue
<control-boton
    @incrementar="incrementar"
    @reiniciar-contador="contador = 0"
>
</control-boton>
```


