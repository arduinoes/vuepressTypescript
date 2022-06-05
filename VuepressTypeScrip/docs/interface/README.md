---
sidebar: auto
---

# Comenzando

## Asignado Tipos

### Interface

A través de la palabra reservada **interface** podemos asignar que tipo de datos queremos para nuestros objetos, luego mediante **: NombreInterface** nuestros objetos obtienen el tipo de dato. 

```js
interface InfoApp {
  nombre: string
  texto: string
}

const infoApp: InfoApp = reactive({
  nombre: 'Contador',
  texto: 'Vamos a contar'
})
```

### Aplicando tipos directamente I

```js
const contador = ref<number | string>(0);

function incrementar() {
  if (typeof contador.value === "number")
  contador.value ++
  }
```
### Aplicando tipos directamente II

También podemos asignar el tipo de dato directamente mediante **: tipoDato**

#### script

```js
function incrementar(num: number) {
  if (typeof contador.value === "number")
  contador.value += num
  }
```
#### template

```vue
 <button @click="incrementar(2)">Incrementar</button>
```

### Enum 

Podemos enumerar una lista de opciones disponibles personalizadas, ponemos un nombre y a continuación escribimos las opciones. Funciona como un array asignado un número a cada opción. Podremos ver la opción a través de su posición.

```js
enum Temporada {
  primavera,
  verano,
  otono,
  invierno
}

const temporada = ref<Temporada> (Temporada.invierno)
```
```vue
  <h1>{{ temporada }}</h1>  
  <h1>{{ Temporada[temporada] }}</h1>
```
### Export default interface

typescript > interface.ts

```js
export default interface Persona {
    nombre: string,
    apellido: string
  }
```

views > HelloView.vue

```js
import type Persona from '@/typescript/interfaces';

const persona: Persona = reactive ({
  nombre: 'Carlos',
  apellido: 'Miranda'
})
```

```vue
<h1>{{ persona.nombre + ' ' + persona.apellido }}</h1>
```
