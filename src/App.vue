<template>
  <div id="app">
    <MainHeader/>
    <GPBar/>
    <ContentBox/>
    <ChartBox/>
    <RecommandVideo/>
  </div>
</template>

<script>
import MainHeader from './components/MainHeader.vue'
import GPBar from './components/GPbar.vue'
import ContentBox from './components/ContentBox.vue'
import ChartBox from './components/ChartBox.vue'
import RecommandVideo from './components/RecommandVideo.vue'

export default {
  name: 'App',
  components: {
    MainHeader,GPBar,ContentBox,ChartBox,RecommandVideo
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
  margin: 0;
}
</style>
