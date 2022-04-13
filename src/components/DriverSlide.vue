<template>
  <div id="driver">
  <img :src="require(`@/assets/driverimg/${current.picture}`)" :alt="current.name" key="1">
  <h3 key="2">{{ current.name }}</h3>
  <p key="3">{{ current.number }}</p>
  <p key="4">{{ current.team }}</p>
  <p key="5">point : {{ current.point }}</p>
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
      return this.drivers[this.index%this.drivers.length];
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

.pre {
  float: left;
}

.next {
  float: right;
}
</style>
