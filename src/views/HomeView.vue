<template>
  <div class="home">
    <img alt="Vue logo" src="../assets/logo.png">
    <Titulo texto="Página de Inicio"/>
    
  </div>
</template>

<script>
import Titulo from '../components/Titulo'

export default {
  name: 'HomeView',
  components: {
   Titulo
  }
}
</script>
