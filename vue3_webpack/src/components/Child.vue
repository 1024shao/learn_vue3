<template>
  <div class="child">
    <h2>child组件</h2>
    <Son />
  </div>
</template>

<script>
import Son from './Son.vue'
export default {
  components: {
    Son
  }
}
</script>

<style>
.child {
  height: 200px;
  background-color: aquamarine;
}
</style>