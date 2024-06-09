

<template>
  <h1>{{ mensaje }}</h1>
  <h1>invertido : {{ invertido }}</h1>
  <input type="text" v-model="mensaje">
</template>

<script>
import { computed } from 'vue'
export default{
  data(){
    return{
      mensaje : "hola soy esteban"
    }
  },

  //la propiedad computed nos permite hacer operacion entre nuestros datos , basicamente es hacer una funcion que modifica algo de data y lo podemos llamar en nuestro html
  computed:{
    invertido : function(){
      return this.mensaje.split('').reverse().join('');
    }
  }


}

</script>


<style scoped>


</style>
