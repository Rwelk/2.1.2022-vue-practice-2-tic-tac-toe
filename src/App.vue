<template>
  <div class="app">
    
    <!-- Should have a title for the page in h1  -->
    <h1>Tic Tac Toe</h1>

    <!-- Should have any instructions or notes under the board  -->
    <p>Literally just Tic Tac Toe. X goes first.</p>

    <!-- Should have a TicTacToeBoard component in the template  -->
    <TicTacToeBoard/>
    
  </div>
</template>

<script>
  import TicTacToeBoard from './components/TicTacToeBoard'

  export default {
    name: 'App',
    components: {
      TicTacToeBoard
    }
  }
</script>

<style>
  #app {
    font-family: 'Lucida', Helvetica, Arial, sans-serif;
    font-size: 175%;
    font-weight: bold;
    -webkit-text-stroke-width: 1px;
    -webkit-text-stroke-color: black;
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;
    text-align: center;
    color: #ffffff;
    
    background-image: url('./assets/plaid_design.png');
    height: 100vh;
    width: 95vw;
  }

  body {
    margin: 0;
    padding: 0;
  }
</style>

<style scoped>
  h1 {
    padding-top: 20px;
  }
  
  div.background {
    background-image: url('./assets/plaid_design.png');
  }

</style>