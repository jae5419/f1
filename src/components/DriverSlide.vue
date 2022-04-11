<template>
  <div id="driver">
  <img src="../assets/icon/racing.png" :alt="drivers[i].name">
  <h2>{{ drivers[i].name }}</h2>
  <p>{{ drivers[i].number }}</p>
  <p>{{ drivers[i].team }}</p>
  <p>{{ drivers[i].point }}</p>
  <button @click="pre">pre</button>
  <button @click="next">next</button>
  </div>
</template>

<script>
import data from '../data.json'

export default {
  name: 'DriverSlide',
  data: function() {
    return {
      drivers: data.drivers,
      index: 0
    }
  },
  methods: {
    pre: function() {
      this.index--;
      clearInterval(this.autoplay);
    },
    next: function() {
      this.index++;
      clearInterval(this.autoplay);
    }
  },
  computed: {
    i: function() {
      return this.index%this.drivers.length;
    }
  },
  created: function() {
    this.autoplay=setInterval(() => {this.index++;}, 5000);
  }
}
</script>

Vue.component('drivers-component', {
  template: `<div id="driver">
  <img :src="driver[current].picture" :alt="driver[current].name">
  <h2>{{ driver[current].name }}</h2>
  <p>{{ driver[current].number }}</p>
  <p>{{ driver[current].team }}</p>
  <p>{{ driver[current].point }}</p>
  <button @click="pre">pre</button>
  <button @click="next">next</button>
  </div>
  data: function() {
    return {
      driver: [{picture: "./img/racing.png", name: "Max Verstappen", number: "1", team: "Red Bull Racing", point: "25"},
      {picture: "./img/racing.png", name: "Daniel Ricciardo", number: "3", team: "McLaren", point: "8"},
      {picture: "./img/racing.png", name: "Lando Norris", number: "4", team: "McLaren", point: "16"},
      {picture: "./img/racing.png", name: "Sebastian Vettel", number: "5", team: "Aston Martin", point: "0"},
      {picture: "./img/racing.png", name: "Nicholas Latifi", number: "6", team: "Williams", point: "0"},
      {picture: "./img/racing.png", name: "Pierre Gasly", number: "10", team: "AlphaTauri", point: "6"},
      {picture: "./img/racing.png", name: "Sergio Perez", number: "11", team: "Red Bull Racing", point: "30"},
      {picture: "./img/racing.png", name: "Fernando Alonso", number: "14", team: "Alpine", point: "2"},
      {picture: "./img/racing.png", name: "Charles Leclerc", number: "16", team: "Ferrari", point: "71"},
      {picture: "./img/racing.png", name: "Lance Stroll", number: "18", team: "Aston Martin", point: "0"},
      {picture: "./img/racing.png", name: "Kevin Magnussen", number: "20", team: "Hass F1 Team", point: "12"},
      {picture: "./img/racing.png", name: "Yuki Tsunoda", number: "22", team: "AlphaTauri", point: "4"},
      {picture: "./img/racing.png", name: "Alexander Albon", number: "23", team: "Williams", point: "1"},
      {picture: "./img/racing.png", name: "Zhou Guanyu", number: "24", team: "Alfa Romeo", point: "1"},
      {picture: "./img/racing.png", name: "Nico Hulkenberg", number: "27", team: "Aston Martin", point: "0"},
      {picture: "./img/racing.png", name: "Esteban Ocon", number: "31", team: "Alpine", point: "20"},
      {picture: "./img/racing.png", name: "Lewis Hamilton", number: "44", team: "Mercedes", point: "28"},
      {picture: "./img/racing.png", name: "Mick Schumacher", number: "47", team: "Hass F1 Team", point: "0"},
      {picture: "./img/racing.png", name: "Carlos Sainz", number: "55", team: "Ferrari", point: "55"},
      {picture: "./img/racing.png", name: "George Russell", number: "63", team: "Mercedes", point: "37"},
      {picture: "./img/racing.png", name: "Valtteri Bottas", number: "77", team: "Alfa Romeo", point: "12"}
    ],
      index: 0
    }
  },
  methods: {
    pre: function() {
      this.index--;
      clearInterval(this.autoplay);
    },
    next: function() {
      this.index++;
      clearInterval(this.autoplay);
    }
  },
  computed: {
    current: function() {
      return this.index%20;
    }
  },
  created: function() {
    this.autoplay=setInterval(() => {this.index++;}, 5000);
  }
})