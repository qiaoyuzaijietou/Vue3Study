<template>
  <div class="app">
    <h3>我是App组件</h3>
    <suspense>
      <template #default>
        <Child />
      </template>
      <template #fallback>
        <h3>稍等，加载中...</h3>
      </template>
    </suspense>
  </div>
</template>

<script>
import { defineAsyncComponent } from "vue";
// import Child from './components/Child' //静态引入
const Child = defineAsyncComponent(() => import("./components/Child.vue")); //异步引入
export default {
  name: "App",
  components: {
    Child,
  },
};
</script>

<style>
.app {
  background-color: gray;
  padding: 10px;
}
</style>