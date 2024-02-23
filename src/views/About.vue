<template>
  <div class="about">
    <h1>アバウト</h1>
    <!-- <h3>{{searchFunction}}</h3> -->
    <input type="text" v-model="search" ref="name">
    <div>検索言葉は　－{{search}}</div>
    <div class="colrNameAge" :key="name" v-for="name in searchFunction">{{name}}</div>
  </div>
</template>

<script>
import { computed, reactive, ref, watch, watchEffect } from 'vue'

export default {
  name: 'About',
  setup(){

  const search =  ref('')
  const names  =  ref(['The Gazebo','The Country Style','The World Says Hello'])
  const searchFunction = computed(()=>{
    return names.value.filter((name)=>name.includes(search.value))
  })
  watch(search,()=>{
    console.log('watch function Ran')
  })
  watchEffect(()=> {
    console.log('watchEffect function Ran',search.value)
  })
    return {search,names,searchFunction}
  },
  mounted(){
    const nameElement = this.$refs.name;
    nameElement.focus();
  }

}
</script>
<style scoped>
.colrNameAge{
  background: rgb(222, 13, 13);
  color: rgb(255, 251, 0);
  padding: 15px;
  border-radius: 5px;
  margin: 5px auto;
  max-width: 500px;
}
.colrNameAge:hover {
  color: rgb(222, 13, 13);
  background: rgb(235, 233, 233);
}
</style>
