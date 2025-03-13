<template>
  <!--  // 组件结构-->
  <div class="person">
    <h3>Name:{{person.name}}</h3>
    <h3>Age:{{person.age}}</h3>
    <h3>Car:{{person.car.c1}} and {{person.car.c2}}</h3>
    <button @click="changeAge">改变年龄</button>
    <button @click="changeAge333">改变333年龄</button>
    <h3>水温:{{water.delta}}</h3>
    <h3>水位:{{water.height}}</h3>
    <button @click="changeHeight">水位升高</button>
    <button @click="changeDelta">水温升高</button>
  </div>
</template>

<script lang="ts" setup name="Person2333">
import { ref, reactive, watch, watchEffect } from 'vue'
let person = reactive({
  name:"张三",
  age:19,
  car:{
    c1:"宝马",
    c2:"奥拓"
  }
})
let person333 = ref({
  name:"张三",
  age:19,
  car:{
    c1:"宝马",
    c2:"奥拓"
  }
})
let water = reactive({
  height:10,
  delta:23
})
function changeHeight(){
  water.height += 10;
}
function changeDelta(){
  water.delta += 10;
}
function changeName(){
  person.name = "李四";
}
function changeAge(){
  person.age += 1;
}
function changeCar1(){
  person.car.c1 = "Jeep";
}
function changeCar2(){
  person.car.c2 = "FKKKKKK";
}
function changeAge333(){
  person333.value.age += 1;
}
watch(()=>[person.age,person.name],(newValue, oldValue)=>{
  console.log('person.age变化了',newValue,oldValue);
})
watch(()=>person333.value.age,(newValue,oldValue)=>{
  console.log('person333的age变化了',newValue,oldValue);
})
watchEffect(()=>{
  if(water.height >= 233){
    console.log("水位过高",water.height);
  }
  if(water.delta >= 80){
    console.log("水温过高", water.delta);
  }
})
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
