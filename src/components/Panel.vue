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
  data() {
    return {
      colorCode: this.initialColorCode
    } 
  },
  methods: {
    changeColor () {
      console.log("aaa")
      this.colorCode = "#666666";

      console.log(this.colorCode)
    }
  }

}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.panel {

  padding: 2px 50px;
}
.text {
  font-size: 32px;
}
</style>

