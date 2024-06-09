

<template>
  <div class="container mt-5">
    <!-- clases con vueJS , estamos agragando clases de Bootstrap con vueJS-->
    <div  :class="['p-3','text-white',fondo]">
      <p>Lorem, ipsum dolor sit amet consectetur adipisicing elit. Mollitia quam nisi aperiam repellendus quia reprehenderit tempora magnam expedita provident soluta, asperiores adipisci omnis ullam, molestias sit architecto. Accusantium laudantium quos, assumenda reiciendis quibusdam aspernatur est voluptates quia porro dolorem officia error, numquam architecto corrupti iusto, eligendi hic aut dolores voluptate cum? Consequatur non ipsam aliquid nisi impedit consectetur, ex ratione!</p>
    </div>
    <input type="text" class="form-control my-3" v-model="fondo">

    <!-- aqui aplicamos algo parecido a un condicional para las clases -->
     <!-- basicamente lo que le estamos diciendo a VueJs es que si color es true le aplicamos la clase bg-info -->
    <div class="text-white p-3" :class="{'bg-info': color}">
      <p>
          Lorem ipsum dolor sit amet consectetur adipisicing elit. Voluptatibus, magnam deserunt. Dolore adipisci necessitatibus dolores corrupti aliquam et quo eius architecto praesentium repellat, iure, similique tempore optio aperiam. Harum quam minima laudantium eligendi hic soluta, quibusdam quis aut, aperiam pariatur aliquid esse commodi, iure facere? Tenetur eius iusto nemo animi assumenda id quisquam quia voluptas, in magnam voluptatum quo laboriosam.
      </p>

      <!-- hacemos un boton que nos va a permitir cambiar el color o la clase de la cajita de arriba -->
      <button @click="cambiarColor">cambiar Color de esta caja</button>

    </div>
  </div>
</template>

<script >
 export default{
  data(){
    return{
      fondo:'bg-warning',
      color:true,
    }
  },

  methods :{
    cambiarColor : function(){
      this.color = !this.color;
    },

  }


 }

</script>


<style scoped>

</style>
