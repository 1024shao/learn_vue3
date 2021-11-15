<template>
  <div>
    <h2>{{name}}</h2>
    <h2>{{age}}</h2>
    <button @click="sayHello">点我</button>
    <button @click="changeInfo">修改</button>
    <h1>{{obj.type}}</h1>
    <h1>{{obj.address.name}}</h1>
  </div>
</template>

<script>
import { ref } from 'vue'
// 为什么 vue3需要进行引入的方式实现响应式
// 1. 减少体积,不需要花费资源对原本不需要进行响应式的数据进行更改
// 2.
export default {
  name: 'App',
  setup() {
    let name = ref('张三')
    let age = ref(9)
    let obj = ref({
      type: "前端",
      address: {
        name: "长沙"
      }
    })
    let obj2 = ref(['1'])

    function sayHello() {
      alert(`我叫${name},我${age}岁了，你好啊`)
    }
    function changeInfo() {
      console.log(name)
      console.log(obj)
      obj.value.type = '后端'
      obj.value.address.name = '湖南'
      console.log(obj2)
    }
    return {
      name,
      age,
      sayHello,
      changeInfo,
      obj
    }
  }
}
</script>
