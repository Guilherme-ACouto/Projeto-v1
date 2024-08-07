<template>
  <div id="app">
    <!-- Seu conteúdo aqui -->
    <router-view></router-view>
  </div>
</template>

<script>
export default {
  name: 'App',
};
</script>

<style>

body {
  background-color: #d3d3d3;
  margin: 0;
  padding: 0;
}

#app {
  min-height: 100vh;
  display: flex;
  flex-direction: column;
}
</style>
