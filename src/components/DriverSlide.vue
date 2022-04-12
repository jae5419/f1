<template>
  <div id="driver">
  <img :src="require(`@/assets/driverimg/${current.picture}`)" :alt="current.name">
  <h3>{{ current.name }}</h3>
  <p>{{ current.number }}</p>
  <p>{{ current.team }}</p>
  <p>point : {{ current.point }}</p>
  <button @click="pre" class="pre">&lt;</button>
  <button @click="next" class="next">&gt;</button>
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
  width: 38%;
}

#driver img {
  width: 103px;
  height: 103px;
  float: left;
}

.pre {
  display: inline;
  position: relative;
  top: -50%;
  border: none;
  background-color: darkslategray;
  opacity: 0.5;
  color: black;
  font-weight: bold;
}

.next {
  display: inline;
  position: relative;
  top: -50%;
  border: none;
  background-color: darkslategray;
  opacity: 0.5;
  color: black;
  font-weight: bold;
}
</style>