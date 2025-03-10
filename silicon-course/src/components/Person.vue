<template>
  <!--  // 组件结构-->
  <div class="person">
    <p>{{ sum }}</p><br>
    <button @click="changeSum">改变sum</button>
  </div>
</template>

<script lang="ts" setup name="Person2333">
import { ref, watch } from 'vue'

  let sum = ref(-2);
  function changeSum(){
    sum.value++;
  }
  const stopWatch = watch(sum, (newVal, oldVal) => {
    console.log("发生变化"+newVal+" "+oldVal);
    if(newVal>=10){
      stopWatch(newVal);
    }
  })
  console.log(stopWatch);
  console.log(watch(sum, (newVal, oldVal) => {}))
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
