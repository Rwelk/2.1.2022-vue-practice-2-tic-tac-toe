<template>
  <div>
    <ui v-for="i in 3" :key="i">
      <li v-for="j in 3" :key="j">
        <Cell :value='cellValues[i - 1][j - 1]' :turn='xGoes' @makeTurn="makeTurn(i - 1, j - 1)"/>
      </li>
      <br>
    </ui>
    
    <h2 v-if="winner == 'X'">X Wins!</h2>
    <h2 v-if="winner == 'O'">O Wins!</h2>
    <button v-if="winner">Play again?</button>
  </div>
</template>

<script>
  import Cell from './Cell'

  export default {
    name: 'TicTacToeBoard',
    components: {
      Cell
    },
    data () {
      return {
        xGoes: true,
        cellValues: [[" ", " ", " "], [" ", " ", " "], [" ", " ", " "]],
        winner: '',
      }
    },
    methods: {
      makeTurn (i, j) {
        this.cellValues[i][j] = this.xGoes ? "X" : "O"
        this.xGoes = !this.xGoes
        this.winner = this.check_winner()
      },

      check_winner() {
        if (this.cellValues[0][0] == this.cellValues[0][1] && this.cellValues[0][0] == this.cellValues[0][2]) {
          if (this.cellValues[0][0] == 'X') {
            return 'X'
          }
          else if (this.cellValues[0][0] == 'X') {
            return 'O'
          }
        }
        return ''
      }
    }
  }
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
  h2 {
    display: inline;
  }
  li {
    list-style-type: none;
    display: inline;
  }
</style>
