<template>
  <div id="app">
    <DotSnake/>
    <AnimatedBorder style="display: none"/>
    <BorderAnimation/>
    <LoadingAnimation style="display: none"/>
  </div>
</template>

<script>
import DotSnake from './components/DotSnake.vue'
import AnimatedBorder from './components/AnimatedBorder.vue'
import BorderAnimation from './components/BorderAnimation.vue'
import LoadingAnimation from './components/LoadingAnimation.vue'

export default {
  name: 'App',
  components: {
    DotSnake,
    AnimatedBorder,
    BorderAnimation,
    LoadingAnimation
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
