<template>
  <div id="app">
    <TodoApp/>
  </div>
</template>

<script>
import TodoApp from "./components/TodoApp.vue"

export default {
  name: 'App',
  components: {
    TodoApp
  }
}
</script>

<style>

body{
  background-color: #181824;
}

#app {
  background-image: url(assets/images/bg-desktop-dark.jpg);
  background-repeat: no-repeat;
  background-position: top center;
  background-size: 100%;
  font-size: 18px;
  height: 100vh;
}
</style>
