<template>
  <div class="container mt-5">
    <h3>
      {{ titulo }}
      |
    </h3>
    <input type="text" class="form-control my-3" v-model="nuevaTarea" @keyup.enter="agregarTarea"/>
    <button class="btn btn-primary" @click="agregarTarea" >Agregar</button>
    <button class="btn btn-danger" @click="eliminarTarea">Eliminar Tarea</button>
    <div class="mt-3">
      <div class="alert alert-primary" role="alert">
        A simple primary alert—check it out!
      </div>
    </div>

    <div>
      <ul class="list-group">
        <li class="list-group-item" v-for="(tarea,indice) in tareas" :key="indice">{{ tarea.tarea }} <br> Completada : {{ tarea.completada }}
        <button class="btn btn-warning" @click="completada(indice)">Completada</button>
        <button class="btn btn-danger" @click="eliminar(indice)">eliminar</button>
        </li>
        
      </ul>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      titulo: "Gym con vueJS",
      id: 0 ,
      nuevaTarea: "",
      tareas: [],
    };
  },

  methods: {
    agregarTarea: function () {
      this.tareas.push({ tarea:this.nuevaTarea , completada : false});
      this.nuevaTarea = "";

      //aqui definimos un objeto para usar el local storge , llamado gym-vue y para guardarlo como un objeto las tareas , usamos un json.stringify para trnasformar ese arreglo de objetos
      localStorage.setItem("gym-vue", JSON.stringify(this.tareas))

    },
    eliminarTarea:function(){
      this.tareas.pop();

      localStorage.setItem("gym-vue", JSON.stringify(this.tareas))
    },
    
    completada:function(id_de_la_tarea){
      console.log("entre");
      this.tareas[id_de_la_tarea].completada = !this.tareas[id_de_la_tarea].completada;
      console.log(this.tareas[id_de_la_tarea]);

      localStorage.setItem("gym-vue", JSON.stringify(this.tareas))
    },

    eliminar:function(id_de_la_tarea){
      console.log("entre a eliminar");
      this.tareas.pop(id_de_la_tarea);
    
      localStorage.setItem("gym-vue", JSON.stringify(this.tareas))
    }
  },

  //vamos a usar el localStorage , el created nos permite ejecutar algo justo antes de que la instancia de vue se haya terminado de procesar, por lo que justo cuando abramos esta pagina , se va a almacenar lo del localStorage en la variable almacenamientoDelNavegador , al obtener ese alamacenamiento , guardamos eso en el arreglo tareas
    created:function(){
      let almacenamientoDelNavegador = JSON.parse(localStorage.getItem("gym-vue"))

      if (almacenamientoDelNavegador === null){
        this.tareas = [];

      }else{
        this.tareas = almacenamientoDelNavegador
      }
      console.log(almacenamientoDelNavegador);
    }

};
</script>

<style scoped></style>
