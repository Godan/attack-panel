<template>
  <div class="panel" v-bind:style="{'background-color':colorCode}" v-on:click="changeColor()">
  <p class="text">{{text}}</p>
  </div>
</template> 

<script>
export default {
  name: 'Panel',
  props: {
    initialColorCode: {
      type: String,
      default: "#ffffff"
    },
    text: {
      type: String,
      default: "null"
    }
  },
  inject: ['currentColor'],
  data() {
    return {
      colorCode: this.initialColorCode
    } 
  },
  methods: {
    changeColor () {
      console.log(this.currentColor())
      this.colorCode = this.currentColor();
    }
  }

}
</script> 

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.panel {

  /* padding: 2px 50px; */
  width: 100%;
  height: 100%;  
  display: table-cell; 
  vertical-align: middle;
}
.text {
  font-size: 42px;
  text-align: center;
  vertical-align: middle;
}
</style>

