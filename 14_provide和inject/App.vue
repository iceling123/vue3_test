<template>
  <div class="app">
    <h3>我是App组件(祖)---{{name}}---{{price}}</h3>
    <Child></Child>
  </div>
</template>

<script>
import { reactive, toRefs,provide } from 'vue';
import Child from './components/Child.vue';
export default {
  name: 'App',
  components: {
    Child
  },
  setup() { 
    let car = reactive({
      name: '奔驰',
      price:'30w'
    })
    provide('myCar',car)
    return {
      ...toRefs(car)
    }
  }
}
</script>

<style>
.app{
  background-color: gray;
  padding: 10px;
}
</style>