<template>
  <!--  // 组件结构-->
  <div class="person">
    <h3>Ref基本变量--不需要深度监测---Val1:{{val1}}</h3>
    <button @click="changeVal1">改Val1</button>
    <br>
    <h3>Ref对象变量--未开启深度监测---Val2:{{val2.name}} {{val2.age}}</h3>
    <button @click="changeVal2">改Val2</button>
    <button @click="changeVal2Total">换Val2</button>
    <br>
    <h3>Reactive对象变量---默认开启深度监测----:{{val3.brand}} {{val3.outdate}}</h3>
    <button @click="changeVal3">改Val3</button>
    <button @click="changeVal3Total">换Val3</button>
    <br>
    <h3>Ref复杂嵌套变量----Val4:{{val4.name}} {{val4.age}}</h3>
    <p>Val4 son:{{val4.son.name}} {{val4.son.age}}</p><br>
    <h3>Reactive复杂嵌套变量----Val5:{{val5.brand}} {{val5.outdate}}</h3>
    <p>Val5 maker:{{val5.maker.name}} {{val5.maker.age}}</p><br>
  </div>
</template>

<script lang="ts" setup name="Person2333">
import { ref, reactive, watch } from 'vue'
  // 变量
  let val1 = ref(233);
  let val2 = ref({
    name:"JOJO",
    age:"18"
  })
  let val3 = reactive({
    brand:"宝马",
    outdate:"2000-05-01"
  })
  let val4 = ref({
    name:"Joseph",
    age:"18",
    son:{
      name:"LittleJOJO",
      age: 3
    }
  })
  let val5 = reactive({
    brand:"奥拓",
    outdate:"2077-05-01",
    maker:{
      name:"Ford",
      age:"93"
    }
  })
  // 方法与监视
  function changeVal1(){
    val1.value += 1;
  }
  watch(val1,(newVal,oldVal)=>{
    console.log("Val1 changed",newVal,oldVal);
  })

  function changeVal2(){
    val2.value.name = "JOOOOSISS";
  }
  function changeVal2Total(){
    val2.value = {name:"WERTYUIO", age:"23"};
  }
  watch(val2,(newVal,oldVal)=>{
    console.log("Val2 changed",newVal,oldVal);
  })

  function changeVal3(){
    val3.brand = "法拉利";
  }
  function changeVal3Total(){
    Object.assign(val3,{
      brand:"Jeep",
      outdate:"1002-05-01"
    })
  }
  watch(val3,(newVal,oldVal)=>{
    console.log("Val3 changed",newVal,oldVal);
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
