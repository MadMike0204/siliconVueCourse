<template>
  <!--  // 组件结构-->
  <div class="person">
    <input type="text" v-model="userName" placeholder="Name">
    <input type="text" v-model="userEmail" placeholder="Email"><br><br>
    用户信息: <span>{{infomation}}</span> <br>
  </div>
</template>

<script lang="ts" setup name="Person2333">
import { computed, ref } from 'vue'
  let userName = ref("Joseph")
  let userEmail = ref("joseph@gmail.com")
  let infomation = computed(()=>{
    return "User Name:"+userName.value+"  User Email:"+userEmail.value;
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
