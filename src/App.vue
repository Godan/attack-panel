<template>
  <div style="width: 100%; height: 100%;  margin: 2px;">
    <div v-for="cullentRow of row" :key="cullentRow" style="width: 100%; height: 20%;  margin: 2px;">
      <div class="panel-row" style="width: 100%; height: 100%;   ">
        <div v-for="currentCol of col" :key="currentCol" style="width: 20%; height: 100%; margin: 2px 2px; display: table;" >
          <Panel initialColorCode="#451278" :text="panelNumber(cullentRow, currentCol)" />
        </div>
      </div>
    </div>
    <div style="background-color: red;" v-on:click="changeColor('red')">red</div>
    <div style="background-color: green;" v-on:click="changeColor('green')">green</div>
    <div style="background-color: blue;" v-on:click="changeColor('blue')">blue</div>
    <div style="background-color: yellow;" v-on:click="changeColor('yellow')">yellow</div>
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
      currentCol: 0,
      currentColor: '#ffffff'
    }
  },
  provide: function () {
    return {
      currentColor: () => this.currentColor
    }
  },
  methods: {
    panelNumber(x, y) {
      console.log(x)
      return (this.col * (x - 1)) + y;
    } ,
    changeColor(colorCode){
      this.currentColor = colorCode

      console.log(this.currentColor)
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
  height: 80vh;
}
.panel-row {
  display: flex;
}
</style>
