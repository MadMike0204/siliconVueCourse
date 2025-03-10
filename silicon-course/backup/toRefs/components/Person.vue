<template>
  <!--  // 组件结构-->
  <div class="person">
    <p>{{person.name}}: {{person.age}}</p>
    <button @click="changePerson">换人</button>
  </div>
</template>

<script lang="ts" setup name="Person2333">
import { reactive, toRefs } from 'vue'
  let person = reactive({
    name:"Joseph",
    age:18
  })
  let {name,age} = toRefs(person);
  function changePerson(){
    age.value ++;
    name.value += '~';
    console.log(name.value,person.name);
    console.log(age.value,person.age);
  }

  let joseph = {
    pname:"Joseph",
    page:18,
    pheight:1.6,
    pmajor:"machine"
  }
  let {page,pname,pmajor,pheight} = joseph;
  console.log(page,pname,pmajor,pheight);

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
