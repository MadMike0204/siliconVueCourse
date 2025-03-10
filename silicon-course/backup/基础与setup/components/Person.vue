<template>
  <!--  // 组件结构-->
  <div class="person">
    <h2>Name:{{name}}</h2>
    <h2>Age:{{age}}</h2>
    <button @click="showTel">联系方式</button>
    <button @click="editAge">修改年龄</button>
    <button @click="editName">修改名字</button>
  </div>
</template>

<script lang="ts">
  export default {
    name:'Person',
    setup(){ // setup 里 this实例 没有被维护 不能使用 是undefined
      // 数据(原data) 此时的数据 不是响应式的
      let name = '张三';
      let age = 19;
      let tel = '13812345678';
      // 方法
      // 此时修改name 页面不变化
      function editName(){
        console.log('Edit Name');
        if(name === 'Zhang San')
          name = '张三';
        else
          name = 'Zhang San';
      }
      // 此时修改age 页面不变化
      function editAge(){
        console.log('Edit Age');
        age += 1;
      }
      function showTel(){
        alert(tel);
      }
      return {name,age,tel,editName,editAge,showTel}; // 数据与方法 交出去，内外非同名变量使用  内name:外name
    }
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
