<template>
  <div v-for="cullentRow of row" :key="cullentRow" >
    <div class="panel-row">
      <div v-for="currentCol of col" :key="currentCol" >
        <Panel initialColorCode="#451278" :text="panelNumber(cullentRow, currentCol)"/>
      </div>
    </div>
  </div>
</template>

<script>
import Panel from './components/Panel.vue'

export default {
  name: 'App',
  components: {
    Panel
  },
   data: function () {
    return {
      row: 5,
      col: 5,
      cullentRow: 0,
      currentCol: 0
    }
  },
  methods: {
    panelNumber(x, y) {
      console.log(x)
      return (this.col * (x - 1)) + y;
    } 
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
.panel-row {
  display: flex;
}
</style>
