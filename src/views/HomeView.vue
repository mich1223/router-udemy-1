<template>
  <div class="home">
    <img alt="Vue logo" src="../assets/logo.png">
    <Titulo texto="Título" />
  </div>
</template>

<script>
// @ is an alias to /src
import Titulo from '../components/Titulo'

export default {
  name: 'HomeView',
  components: {
    Titulo
  }
}
</script>
