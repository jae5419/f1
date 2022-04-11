<template>
  <div id="app">
    <MainHeader/>
    <GPBar/>
    <NewsContainer/>
    <DriverSlide/>
    <ChartDriver/>
    <ChartConstructor/>
  </div>
</template>

<script>
import MainHeader from './components/MainHeader.vue'
import GPBar from './components/GPbar.vue'
import DriverSlide from './components/DriverSlide.vue'
import NewsContainer from './components/NewsContainer.vue'
import ChartDriver from './components/ChartDriver.vue'
import ChartConstructor from './components/ChartConstructor.vue'

export default {
  name: 'App',
  components: {
    MainHeader,GPBar,DriverSlide,NewsContainer,ChartDriver,ChartConstructor
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
