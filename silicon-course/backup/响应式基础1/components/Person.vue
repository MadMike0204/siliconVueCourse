<template>
  <!--  // 组件结构-->
  <div class="person">
<!--    <h2>Name:{{name}}</h2>-->
<!--    <h2>Age:{{age}}</h2>-->
<!--    <button @click="showTel">联系方式</button>-->
<!--    <button @click="editAge">修改年龄</button>-->
<!--    <button @click="editName">修改名字</button>-->
<!--    -->
    <ul>
      <li v-for="g in jojo" :key="g.id">
        {{g.id}}:{{g.name}}
      </li>
    </ul>
    <p>{{car.brand}}:{{car.price}}</p>
    <button @click="setBrand">神魔车</button>
    <hr>
    <h2>测试{{layers.a.b.c}}</h2>
  </div>
</template>

<script lang="ts" setup name="Person2333">
  import { reactive } from 'vue'
  import { ref } from 'vue'

  // let name = '张三';
  // let age = 19;
  // const tel = '13812345678';
  // let kb = reactive([
  //   {id:'azzzizi01',name:"steam"},
  //   {id:'azzzizi02',name:"epic"},
  //   {id:'azzzizi03',name:"wegame"}
  // ])

  // ref s
  let x = ref(233)
  // ref d
  let jojo = ref(
    [
      {id:'wcs1',name:'Joseph'},
      {id:'wcs2',name:'Jostar'}
      ]
  )
  // reactive
  let car = reactive({brand:"2333",price:100})
  let jojo2 = reactive(
    [
      {id:'wcs1',name:'Joseph'},
      {id:'wcs2',name:'Jostar'}
    ]
  )
  let layers = {
    a:{
      b:{
        c:600
      }
    }
  };
  function exchangeJojo(){
    let temp = jojo.value[0].name;
    jojo.value[0].name = jojo.value[1].name;
    jojo.value[1].name = temp;
  }
  function setBrand(){
    car.brand="神魔车";
  }
  // function editName(){
  //   console.log('Edit Name');
  //   if(name === 'Zhang San')
  //     name = '张三';
  //   else
  //     name = 'Zhang San';
  // }
  //
  // function editAge(){
  //   console.log('Edit Age');
  //   age += 1;
  // }
  //
  // function showTel(){
  //   alert(tel);
  // }

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
