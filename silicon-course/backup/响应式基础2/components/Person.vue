<template>
  <!--  // 组件结构-->
  <div class="person">
    <ul>
      <li v-for="g in games" :key="g.id">{{g.name}}</li>
    </ul>
    <button @click="changeFirstGame">换名</button>
  </div>
</template>

<script lang="ts" setup name="Person2333">
  import { reactive } from 'vue'
  import { ref } from 'vue'

  const games = ref([
    {id:'josidfe001',name:'极限竞速'},
    {id:'josidfe002',name:'狂飙'},
    {id:'josidfe003',name:'老头环'}
  ])

  function changeFirstGame(){
    games.value[0].name = '流星蝴蝶剑';
    games.value[1].name = '大蛇';
    games.value[2].name = '大蛇设';
  }
  console.log(games);
</script>

<style scoped>
.person{
  background-color: skyblue;
  box-shadow: 0 0 10px;
  border-radius: 10px;
  padding: 20px;
}
button{
  margin: 0 5px;
}
</style>
