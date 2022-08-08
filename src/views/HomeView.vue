<template>
  <div class="home">
    <img alt="Vue logo" src="../assets/logo.png">

    <Titulo texto="Título" />

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
