<template>
  <div style="width: 100%; height: 100%;  margin: 2px;">
    <div v-for="cullentRow of row" :key="cullentRow" style="width: 100%; height: 20%;  margin: 2px;">
      <div class="panel-row" style="width: 100%; height: 100%;   ">
        <div v-for="currentCol of col" :key="currentCol" style="width: 20%; height: 100%; margin: 4px 4px; display: table;" >
          <Panel initialColorCode="#ffffff" :text="panelNumber(cullentRow, currentCol)" />
        </div>
      </div>
    </div>
    <div class="panel-row" style="width: 100%; height: 30px; padding-top: 30px;">
      <div style="background-color: red;width: 20%; " v-on:click="changeColor('red')">red</div>
      <div style="background-color: green; width: 20%;" v-on:click="changeColor('green')">green</div>
      <div style="background-color: blue; width: 20%;" v-on:click="changeColor('blue')">blue</div>
      <div style="background-color: yellow; width: 20%;" v-on:click="changeColor('yellow')">yellow</div>
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
  background-color: #2c3e50;
  margin-top: 20px;
  height: 80vh;
}
.panel-row {
  display: flex;
}
html {
  background-color: #2c3e50;
}
</style>
