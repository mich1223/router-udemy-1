<template>
   <Titulo texto="Ruta con parámetros"/>
   <h2>Parámetro: {{ $route.params.id }}</h2>
</template>

<script>
import Titulo from '../components/Titulo.vue'
export default{
    components:{
        Titulo
    },
    data(){
        return {
            articulo: {}
        }
    },
    methods:{
        async consumirArticulo(){
            try{
                const data=await fetch(`https://jsonplaceholder.typicode.com/posts/${this.$route.params.id}`) /*extrae los datod de la api */
                const objeto=await data.json()
                console.log(objeto)

            }catch(error){
                console.log(error)
            }
        }
    },
    create(){
        this.consumirArticulo()
    }
}
</script>

<style >

</style>