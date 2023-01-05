<template>
  <div id="app">
    <upper-info-vue />
  </div>
</template>

<script>
import upperInfoVue from './components/upperInfo.vue'

export default {
  components: {
    upperInfoVue,
  }
}
</script>

<style lang="scss">
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

#app {
  width: 100%;
  height: 3072px;
  background-image: url('./assets/images/main-bg.png');
  background-size: contain;
  background-repeat: no-repeat;
}
</style>
