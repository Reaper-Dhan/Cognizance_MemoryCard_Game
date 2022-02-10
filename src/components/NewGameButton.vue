<script>
export default {
  props: {
    newPlayer: {
      type: Boolean,
      default: true
    }
  },
  setup(props, ctx) {
    const startNewGame = () => {
      ctx.emit('start-new-game')
    }

    return {
      startNewGame
    }
  }
}
</script>

<template>
  <br>
  <center>
      <h1>Welcome to Memory-Card Game</h1>
  </center>
  <button v-if="newPlayer" @click="startNewGame" :class="$style.button">Start Game</button>
  <button v-else @click="startNewGame" :class="$style.button">Restart Game</button>
  <br>
</template>

<style module>
h1 {
  font-family: 'Permanent Marker', cursive;
  color:rgb(0, 0, 0); width: 400px;
  font-size: 30px;
}
.button {
  background-color: #fffb00;
  color: black;
  padding: 8px 16px 10px;
  display: flex;
  align-items: center;
  margin: 0 auto 30px;
  font-weight: bold;
  font-family: 'Titillium Web', sans-serif;
  font-weight: bold;
  font-size: 1.2rem;
  border: 0;
  border-radius: 10px;
  transition: 0.2s all ease-in;
  border: 5px solid #52f8f8;
}

.button:hover {
  border: 2px solid #ff07c1;
  background-color: #52f8f8;
  color: black;
  transform: translateY(-10px);
}
</style>
