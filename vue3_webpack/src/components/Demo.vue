<template>
  <div>
    <h2>{{sum}}</h2>
    <button @click="sum++">点我+1</button>
  </div>
</template>

<script>
import { ref, watch } from 'vue'
export default {
  setup() {
    let sum = ref(0)
    watch(sum, () => {
      console.log('sum')
    }, {
      immediate: true,
      deep: true,
    })
    return {
      sum
    }

  }

}
</script>

<style>
</style>