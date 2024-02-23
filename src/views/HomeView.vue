<template>
  <div class="home">
    <!-- <p ref="pTag">お客様<span class="colrNameAge">{{name}}</span>、<span class="colrNameAge">{{age}}</span>歳、ようこそ、ホームページへ。。。</p>
    <br><br><hr>
    <button @click="handleClick">次</button>
    <button @click="age++">Age++</button>
    <hr>
    <input type="text" v-model="name"> -->
    <h3>ホームページ</h3>
    <h3>Refsテクノロジー</h3>
    <p>{{customer.name}}さん - {{customer.age}}歳</p>
    <button @click="updateData">お客様のデータ編集</button>
    <!-- reactive  -->
    <h3>Reactiveテクノロジー</h3>
    <p>{{reactiveCustomer.name}} {{reactiveCustomer.age}}</p>
    <button @click="updateData2">リアクティビティーのデータ編集</button>
  </div>
</template>

<script>
import { reactive, ref } from 'vue'

export default {
  name: 'HomeView',
  setup(){
    // const pTag = ref(null)
    // console.log('pTag',pTag)
    // let name = '恵ちゃん'
    // let age  = 26
  //   const name = ref('恵ちゃん')
  //   const age  = ref(26)
  //  const  handleClick = ()=>{
  //   // pTag.value.classList.add('Learn')
  //   // name.value = '小山'
  //   age.value = 30
  //   }
  const customer = ref({name:'木村' , age:30})
  // Reactiveを使って処理します、
  const reactiveCustomer = reactive({name:'須崎',age:35})

  const updateData = ()=>{
    customer.value.age = 25
  }
  // Reactive Function
  const updateData2 = ()=>{
    reactiveCustomer.age = 38
  }
    // return {name,handleClick,age,pTag}
    return {customer,reactiveCustomer,updateData,updateData2}
  },

}
</script>
<style scoped>
.colrNameAge{
  background: rgb(222, 13, 13);
  color: rgb(255, 251, 0);
  padding: 5px;
  border-radius: 5px;
  margin: 5px;
}
</style>
