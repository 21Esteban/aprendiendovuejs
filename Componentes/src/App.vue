<!-- Crear un Componente
Primero, debes definir un componente. Puedes hacerlo en el mismo archivo .vue o en un archivo separado. Aquí tienes un ejemplo de un componente llamado MyComponent -->


<!-- 2. Registrar el Componente
Para usar el componente padre en otro componente o en el componente raíz (App.vue), debes registrarlo.

En el componente raíz (App.vue): -->

<!-- 3. Usar el Componente
Una vez que has registrado el componente, puedes usarlo en el template del componente donde lo registraste.

4. Pasar Props y Emitir Eventos
Para hacer los componentes más dinámicos, puedes pasar datos a través de props y emitir eventos para comunicarse con otros componentes.

Pasar Props:

En padre.vue, define las props que el componente puede recibir: -->


<template>
  <div>
    <h1>este es el archivo app.vue</h1> 
    <padre :saludo="'Saludos desde un componente usando props' "/>
  </div>
</template>

<script>
import padre from './components/padre.vue'



export default {
    data(){
        return {

        }
    },
    components:{
        padre,
    }
}
</script>

<style>

</style>