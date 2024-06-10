<template>
    <div class="py-5 bg-success">
        <h4>Componente Hijo</h4>
        <h5>{{ nombre }}</h5>
    </div>
</template>

<script>
export default {
    name:"ComponenteHijo",
    data(){
        return{
            nombre: "Juan"
        }
    },
    //ahora como queremos enviar data del elemento hijo al padre usamos mounted ,esta comunicacion entre componentes es muy complicado por lo que en las proximas guias vamos a usar VUEX que nos permite la comunicacion entre componentes .
    mounted(){
        this.$emit();
    }
}
</script>

<style>

</style>