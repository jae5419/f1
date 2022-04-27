<template>
  <div id="driver">
  <transition-group name="fade">
    <div v-for="(driver, i) in drivers" :key="driver.number" id="card">
      <img :src="require(`@/assets/driverimg/${driver.picture}`)" :alt="driver.name" v-if="i==current">
      <h3 v-if="i==current">{{ driver.name }}</h3>
      <p v-if="i==current">{{ driver.number }}</p>
      <p v-if="i==current">{{ driver.team }}</p>
      <p v-if="i==current">point : {{ driver.point }}</p>
    </div>
  </transition-group>
  <button @click="pre" class="pre"><font-awesome-icon :icon="['fas', 'chevron-left']" /></button>
  <button @click="next" class="next"><font-awesome-icon :icon="['fas', 'chevron-right']" /></button>
  </div>
</template>

<script>
import data from '../data.json'

export default {
  name: 'DriverSlide',
  data: function() {
    return {
      drivers: data.drivers.sort(function(a, b) {return b.point-a.point}),
      index: 0
    }
  },
  methods: {
    pre: function() {
      if(this.index>0)
      {
        this.index--;
      }
      else
      {
        this.index=this.drivers.length-1;
      }
      clearInterval(this.autoplay);
    },
    next: function() {
      this.index++;
      clearInterval(this.autoplay);
    }
  },
  computed: {
    current: function() {
      return this.index%this.drivers.length;
    },
    currentImg: function() {
      return this.drivers[this.index].picture;
    }
  },
  created: function() {
    this.autoplay=setInterval(() => {this.index++;}, 5000);
  }
}
</script>

<style>
#driver {
  width: 30%;
  margin: 0 20px;
  padding: 20px;
  background-color: beige;
  position: relative;
}

#driver img {
  width: 103px;
  height: 103px;
  display: inline;
}

#driver button {
  border: none;
  border-radius: 5px;
  background-color: dimgray;
  opacity: 0.45;
  padding: 5px 5px;
  z-index: 100;
}

.fade-enter-active,
.fade-leave-active {
  transition: all 0.3s ease;
  overflow: hidden;
  visibility: visible;
  position: absolute;
  width:100%;
  opacity: 1;
}
.fade-enter,
.fade-leave-to {
  visibility: hidden;
  width:100%;
  opacity: 0;
}

.pre {
  float: left;
}

.next {
  float: right;
}
</style>
