<template>
  <div class="about">
    <Titulo texto="Sobre Nosotros"/>
  </div>
</template>
import Titulo from '../components/Titulo'
export default {
    components: {
        Titulo
    },
    data() {
        return {
            articulo: {}
        }
    },
    methods: {
        async getArticulo() {
            try {
                console.log(this.$route.params.id)
                const data = await fetch(`https://jsonplaceholder.typicode.com/posts/${this.$route.params.id}`)
                const objeto = await data.json()
                this.articulo = objeto;
            } catch (error) {
                console.log(error)
            }
        }
    },
    created() {
        this.getArticulo()
    }
}

<script >
import Titulo from '../components/Titulo.vue'
  export default{
    components:{
        Titulo
    }
  }

</script>

<style>

</style>
