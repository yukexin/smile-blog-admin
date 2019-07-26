<template>
  <div id="app">
    <router-view></router-view>
  </div>
</template>

<script>
  import Vue from 'vue'

  export default {
    data() {
      return {
        // 事件中心
        eventBus: new Vue
      }
    },

    mounted() {
      // 获取将其隐藏
      document.getElementById('loader').style.display = 'none'
    },

    /* data
       provide
       created  // 在这个阶段$el还未生成，在这先处理privide的逻辑，子孙组件才可以取到inject的值
       mounted
    ... */

    /* 允许在父组件向子组件注入vue实例，存在的上下游关系永远存在 */
    provide() {
      return {
        eventBus: this.eventBus
      }
    }
  }
</script>

<style lang="scss" scoped>
  #app {
    width: 100%;
    height: 100%;
  }
</style>

