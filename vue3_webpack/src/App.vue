<template>
  <div class="father">
    <h2>我是父组件</h2>
    <Suspence>
      <template #default>
        <Child />
      </template>
      <template #fallback>
        <h2>is loading</h2>
      </template>
    </Suspence>
  </div>
</template>

<script>
// import Child from './components/Child.vue'
import { defineAsyncComponent } from 'vue'
const Child = defineAsyncComponent(() => import('./components/Child.vue'))
export default {
  components: {
    Child
  }
}
</script>

<style>
.father {
  background-color: saddlebrown;
  height: 400px;
}
</style>