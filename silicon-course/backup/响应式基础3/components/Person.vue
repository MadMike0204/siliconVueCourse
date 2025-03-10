<template>
  <!--  // 组件结构-->
  <div class="person">
    <ul>
      <li v-for="g in games" :key="g.id">{{g.name}}</li>
    </ul>
    <button @click="changeFirstGame">换名</button>
    <h3>{{car.brand}}的价格:{{car.price}}</h3>
    <button @click="changePrice">修改价格</button>
    <button @click="changeCar">换车</button>
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
  const car = reactive({brand:"法拉利",price:2333333})

  function changeFirstGame(){
    games.value[0].name = '流星蝴蝶剑';
    games.value[1].name = '大蛇';
    games.value[2].name = '大蛇设';
  }
  function changePrice(){
    car.price += 10;
  }
  // 对于reactive响应式属性，Object提供的assign(objTarget,objSource)接口，可以将objTarget传递给objSource同时不破坏响应属性(页面同步更新)
  // 如果服务器返回一个包括超量属性的object，再使用.访存每个属性会使得代码冗杂，使用assign整体代替
  // 对于ref属性，可以直接使用.value进行替换，使用.value就代表变量可能被改变，响应式不会被破坏(包了层壳,eg:buffer构造)，不能越过ref改属性
  function changeCar(){
    let serverCar = {brand:"奥拓",price:233}
    Object.assign(car,serverCar);
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
