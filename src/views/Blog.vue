<template>
    <Titulo  texto="Título de Blog" />
    <!--<button @click="consumirApi">Consumir API</button>--> <!--Botón para llamar metodo consumir api-->
    
    <div v-for="item in arrayBlog" :key="item.id"><!--Ciclo para imprimir los títulos del array -->
        <router-link :to="`/blog/${item.id}`">
                {{ item.id }} - {{ item.title }}
        </router-link>
    </div>
</template>

<script>
  import Titulo from '../components/Titulo.vue'
  export default{
    components:{
        Titulo
    },
    data(){
        return{
            arrayBlog: []
        }
    },
    methods:{
        
        async consumirApi() { /*metodo imprimir api */
            try{
                const data = await fetch('https://jsonplaceholder.typicode.com/posts')/*lee el archivo de la url y los guarda en la data*/
                const array = await data.json() /*guarda los datos de data.json  en el array*/
                console.log(array) /*imrime el array */
                this.arrayBlog= array; /*Guarda la información de array */
            }catch (error){
                console.log(error)/*imprime error en caso de haberlo */
            }
        }
    },
    created(){ /*hacer que cargue primero el método que el template */
        this.consumirApi()
    }
  }
</script>

<style>

</style>