<template>
  <!-- Creacion de un componente en VueJS en este caso un formulario basico para guardar informacion  -->

  <!-- aqui creamos el formulario y le agregamos el @submit.prevent="submitForm" para evitar la recarga de la pagina por defecto del navegador -->
  <form @submit.prevent="submitForm">
    <!-- Campo de texto para la fruta la propiedad v-model nos permite obtener los datos de el input y guardarlos , es algo bidireccional , ademas el keyUp nos permite hacer que al darle enter el formulario se envie-->
    <div class="mb-3">
      <label for="exampleInputEmail1" class="form-label"
        >Ingrese la fruta a agregar</label
      >
      <input
        type="text"
        class="form-control"
        id="exampleInputEmail1"
        v-model="fruta_a_guardar"
        @keyup.enter="agregarFruta"
      />
    </div>

    <!-- Botón para enviar el formulario -->

    <button type="submit" class="btn btn-primary" @click="agregarFruta">
      guardar en el carrito
    </button>
  </form>

  <!-- Aqui mostramos las frutas iterando sobre el arreglo  -->
  <div>
    <h1>Frutas</h1>
    <ul>
      <li v-for="(fruta, i) in frutas" :key="fruta[i]">
        {{ fruta }}
      </li>
    </ul>

    <!-- Comprobamos si existen frutas, si no hay se muestra el span -->

    <span v-if="frutas.length === 0">No hay frutas</span>

    <h2>Numero de frutas : {{ numFrutas }}</h2>
    
  </div>
</template>

<script>
export default {
  data() {
    return {
      fruta_a_guardar: "",
      frutas: ["manzana", "pera", "banana", "naranja"],
      numFrutas : 4

    };
  },
  //los metodos solo se ejecutan cuando los llamamos
  methods: {
    agregarFruta: function () {
      console.log("acabo de dar click y voy a guardar la fruta");
      this.frutas.push(this.fruta_a_guardar);
      this.fruta_a_guardar = "";
    },
  },

  computed:{
    //las propiedades computadas o metodos computados son basicamente metodos que van a cambiar o modificar una variable de nuestra data pero mutandolas (haciendo alguna operacion con ella)
  },

  
};
</script>

<style></style>
