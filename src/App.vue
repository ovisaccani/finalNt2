<template>
  <div id="app" class="container mt-3">
    <div class="jumbotron">
      <h1>Final NT2</h1>
      <br>
      <Final />

    </div>
  </div>
</template>

<script>
import Final from './componentes/Final.vue'

export default {
  name: 'App',
  components: {
    Final
  }
}
</script>

<style>
#app {
}

h1 {
  color: blue;
}
</style>
