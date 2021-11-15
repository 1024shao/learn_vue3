<template>
  <div>
    <h2>{{name}}</h2>
    <h2>{{age}}</h2>
  </div>
</template>

<script>
import { ref } from 'vue'
// 为什么 vue3需要进行引入的方式实现响应式
// 1. 减少体积,不需要花费资源对原本不需要进行响应式的数据进行更改
// 2.
export default {
  name: 'App',
  
}
</script>
