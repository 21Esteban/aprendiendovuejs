<template>
  <div class="p-5 bg-dark text-white">
    <h2>{{ saludo }}</h2>
    <hijo/>
  </div>
</template>

<script>
import hijo from './hijo.vue';

export default {
    name: "ComponentePadre",
    props:{
        saludo:{
            type:String,
            required:true,
        }
    },
    
    data(){
        return {
            saludo:"Saludos desde el componente padre"
        }
    },

    components:{
       hijo, 
    }
}
</script>

<style>

</style>