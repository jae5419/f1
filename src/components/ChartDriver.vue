<template>
  <chart-component :list="drivers">
  <template #header>
  <th>이름</th><th>소속팀</th><th>포인트</th>
  </template>
  <template #list="{row}">
  <td>{{ row.name }}</td>
  <td>{{ row.team }}</td>
  <td>{{ row.point }}</td>
  </template>
  </chart-component>
</template>

<script>
import ChartComponent from './Chart.vue'
import data from '../data.json'

export default {
  name: 'ChartDriver',
  components: {
    ChartComponent
  },
  data: function() {
    return {
      drivers: data.drivers
    }
  }
}
</script>

Vue.component('driver-chart', {
  template: `<chart-component :list="drivers">
  <template #header>
  <th>이름</th><th>소속팀</th><th>포인트</th>
  </template>
  <template #list="{row}">
  <td>{{ row.name }}</td>
  <td>{{ row.team }}</td>
  <td>{{ row.point }}</td>
  </template>
  </chart-component>
  data: function() {
    return {
      drivers: [{picture: "./img/racing.png", name: "Max", birth: "1999", team: "RedBull", point: "25"},
      {picture: "./img/racing.png", name: "Ham", birth: "1999", team: "RedBull", point: "25"},
      {picture: "./img/racing.png", name: "Lec", birth: "1999", team: "RedBull", point: "25"},
      {picture: "./img/racing.png", name: "Max", birth: "1999", team: "RedBull", point: "25"},
      {picture: "./img/racing.png", name: "Max", birth: "1999", team: "RedBull", point: "25"},
      {picture: "./img/racing.png", name: "Max", birth: "1999", team: "RedBull", point: "25"},
      {picture: "./img/racing.png", name: "Max", birth: "1999", team: "RedBull", point: "25"},
      {picture: "./img/racing.png", name: "Max", birth: "1999", team: "RedBull", point: "25"},
      {picture: "./img/racing.png", name: "Max", birth: "1999", team: "RedBull", point: "25"},
      {picture: "./img/racing.png", name: "Max", birth: "1999", team: "RedBull", point: "25"},
      {picture: "./img/racing.png", name: "Max", birth: "1999", team: "RedBull", point: "25"},
      {picture: "./img/racing.png", name: "Max", birth: "1999", team: "RedBull", point: "25"},
      {picture: "./img/racing.png", name: "Max", birth: "1999", team: "RedBull", point: "25"},
      {picture: "./img/racing.png", name: "Max", birth: "1999", team: "RedBull", point: "25"},
      {picture: "./img/racing.png", name: "Max", birth: "1999", team: "RedBull", point: "25"},
      {picture: "./img/racing.png", name: "Max", birth: "1999", team: "RedBull", point: "25"},
      {picture: "./img/racing.png", name: "Max", birth: "1999", team: "RedBull", point: "25"},
      {picture: "./img/racing.png", name: "Max", birth: "1999", team: "RedBull", point: "25"},
      {picture: "./img/racing.png", name: "Max", birth: "1999", team: "RedBull", point: "25"},
      {picture: "./img/racing.png", name: "Max", birth: "1999", team: "RedBull", point: "25"}]
    }
  }
});