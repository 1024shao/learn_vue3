<template>
  <div>
    <h2>{{sum}}</h2>
    <button @click="sum++">点我+1</button>
    <hr>
    <h2>鼠标坐标为:X:{{point.x}} Y:{{point.y}}</h2>
    <hr>
    <h2>{{name}}</h2>
    <h2>{{age}}</h2>
    <button @click="age++">age+++</button>
    <hr>
    <button @click="showRowData">展示原始数据</button>
  </div>
</template>

<script>
import { ref, reactive, toRefs, toRaw } from 'vue'
import usePoint from '../hooks/usePoint'
export default {
  setup() {
    let sum = ref(0)
    let point = usePoint()
    let person = reactive({
      name: '占山',
      age: 20
    })

    function showRowData() {
      console.log(sum)
      let sum1 = toRaw(sum)
      console.log(sum1)
    }

    return {
      sum,
      point,
      ...toRefs(person),
      showRowData
    }

  }

}
</script>

<style>
</style>