<template>
  <!--  // 组件结构-->
  <div class="person">
    <h3>姓名:{{person.name}}</h3>
    <h3>年龄:{{person.age}}</h3>
    <h3>公司:{{person.inc}}</h3>
    <button @click="changeAge">更改年龄</button>
    <button @click="changeInc">更改公司</button>
    <button @click="stopWatchSJ">停止石坚</button>
    <button @click="changePerson">换成李四</button>
  </div>
</template>

<script lang="ts" setup name="Person2333">
import { ref, watch } from 'vue'
  let person = ref({
    name:"张三",
    age: 18,
    inc: "Joseph Inc."
  })
  function changeAge() {
    person.value.age += 1;
  }
  function changeInc() {
    person.value.inc += "~";
  }
  function changePerson(){
    person.value = {
      name:"李四",
      age:188,
      inc: "Joseph Inc."
    }
  }
  const stopWatch = watch(person, (newValue,oldValue) => {
    console.log("Person改变了",newValue,oldValue);
  },{ immediate: true,deep: true })
  function stopWatchSJ(){
    stopWatch();
  }

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
