

<template>
  <div class="nav" :class="{dark: theme === dark}">
    <h1>welcome to vue</h1>
  </div>
</template>

<script>
   export default {
    props:['theme']
   }
</script>

<style scoped>
  .nav{
    background-color: brown;
    padding: 5px 2px;
    color: white;
    width: 100%;
  }

  .dark{
    background-color: black;
  }
</style>