<template>
  <button :class="childClass" @click="makeTurn">{{ this.value }}</button>
</template>

<script>
export default {
  props: ['turn'],

  data () {
    return {
      childClass: "",
      value: " ",
    }
  },
  methods: {
    makeTurn () {
      // console.log(this.turn)
      this.childClass = this.turn ? "X" : "O"
      this.value = this.turn ? "X" : "O"
      this.$emit('makeTurn')
    }
  },
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
  button {
    width: 175px;
    height: 175px;
    font: 100px Arial;
    font-weight: bold;
    background-color: rgba(255, 255, 255, .3);
  }
  .X {
    color: orangered;
  }
  .O {
    color: yellow;
  }
</style>
