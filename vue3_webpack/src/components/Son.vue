<template>
  <div class="son">
    <h2>我是son组件</h2>
    <button @click="isShowDialog=true">点击弹出对话框</button>
    <teleport to='body'>
      <div v-if="isShowDialog"
           class="mask">
        <div class="dialog">
          <h4>标题</h4>
          <h5>一些内容</h5>
          <h5>一些内容</h5>
          <h5>一些内容</h5>
          <h5>一些内容</h5>
          <button @click="isShowDialog=false">点击退出对话框</button>
        </div>
      </div>
    </teleport>
  </div>
</template>

<script>
import { ref } from '@vue/reactivity'
export default {
  setup() {
    let isShowDialog = ref(false)
    return {
      isShowDialog
    }
  }
}
</script>

<style>
.son {
  height: 100px;
  background-color: red;
}
.mask {
  position: absolute;
  top: 0;
  bottom: 0;
  left: 0;
  right: 0;
  background-color: rgba(0, 0, 0, 0.5);
}
.dialog {
  position: absolute;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
  height: 300px;
  width: 300px;
  background-color: green;
  text-align: center;
}
</style>