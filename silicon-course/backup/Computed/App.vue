<template>
<!--  // 组件结构-->
  <div class="app">
    <h1>test</h1>
    <person></person>
  </div>
</template>

<script lang="ts">
  import Person from './components/Person.vue'

  export default {
    name: 'App', // 组件名
    components: {Person} //注册组件
  }
</script>

<style>
  .app{
    background-color: white;
    box-shadow: 0 0 10px;
    border-radius: 10px;
    padding: 20px;
  }
</style>
