<template>
  <div class="p-5 bg-dark text-white">
    <h2>{{ saludo }}</h2>
  </div>
</template>

<script>
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
    }
}
</script>

<style>

</style>