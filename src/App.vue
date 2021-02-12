<template>
  <div id="app">
    <ToDo>

    </ToDo>
  </div>
</template>

<script>

import ToDo from "@/components/ToDo";

export default {
  name: 'App',
  components: {
    ToDo
  }
}
</script>

<style>
body{
  background-color: #2c3e50 !important;
}
#app {
  font-family: cursive;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #32ddae;
  margin-top: 60px;
}


</style>
