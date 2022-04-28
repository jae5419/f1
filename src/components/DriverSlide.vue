<template>
  <swiper class="swiper" :options="swiperOption">
    <swiper-slide v-for="(driver, i) in drivers" :key="i">
      <div>
        <img :src="require(`@/assets/driverimg/${driver.picture}`)" :alt="driver.name">
        <h3>{{ driver.name }}</h3>
        <p>{{ driver.number }}</p>
        <p>{{ driver.team }}</p>
        <p>point : {{ driver.point }}</p>
      </div>
    </swiper-slide>
    <div class="swiper-button-prev" slot="button-prev"></div>
    <div class="swiper-button-next" slot="button-next"></div>
  </swiper>
</template>

<script>
import data from '../data.json'
import {swiper, swiperSlide} from 'vue-awesome-swiper'
import 'swiper/css/swiper.css'

export default {
  name: 'DriverSlide',
  components: {swiper, swiperSlide},
  data: function() {
    return {
      drivers: data.drivers.sort(function(a, b) {return b.point-a.point}),
      index: 0,
      swiperOption: {
        slidesPerView: 1,
        spaceBetween: 30,
        loop: true,
        navigation: {
          nextEl: '.swiper-button-next',
          prevEl: '.swiper-button-prev'
        }
      }
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

.swiper {
  height: 300px;
  width: 100%;
}

.swiper .swiper-slide {
  display: flex;
  justify-content: center;
  align-items: center;
  text-align: center;
}
</style>
