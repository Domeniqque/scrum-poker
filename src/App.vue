<template>
  <div id="app">
    <header>
      <img src="./assets/poker.svg" width="40" alt="Scrum Poker">
      <h1>Scrum <span>Poker</span></h1>
    </header>
    <main>
      <card v-for="(value, index) in sequence" 
        :key="index"
        :number="value"
        @click.native="selected = value">
      </card>

      <show-card
        v-if="selected"
        :selected="selected"
        @close="selected = null"/>
    </main>
  </div>
</template>

<script>
import Card from './components/Card'
import ShowCard from './components/ShowCard'

export default {
  name: 'app',
  components: {
    Card,
    ShowCard
  },

  data () {
    return {
      sequence: [1, 2, 3, 5, 8, 13, 21],
      selected: null
    }
  }
}
</script>

<style>
:root {
  --primary-color: #6D5BF0;
}

body {
  margin: 0;
  position: relative;
}

#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: #2c3e50;
}

main {
  text-align: center;
  display: grid;
  grid-template-columns: 1fr 1fr;
}

@media screen and (min-width: 540px) {
  #app {
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
  }
  main {
    grid-template-columns: 1fr 1fr 1fr;
    width: 500px;
  }
}

header {
  margin: 0;
  height: 80px;
  padding: 0 16px 0 24px;
  display: flex;
  justify-content: center;
  flex-direction: row;
  align-items: center;
}

header h1 {
  display: inline-block;
  position: relative;
  font-size: 1.5rem;
  line-height: 1;
  letter-spacing: .02em;
  font-weight: 300;
  box-sizing: border-box;
  padding-left: 10px;
}

header h1 span {
  color: var(--primary-color);
  font-weight: 500;
}

header img {
  padding-left: 15px;
}


@keyframes click_effect {
  50% {
    transform: scale(1.5, 1.5);
    opacity: 0;
  }
  99% {
    transform: scale(0.001, 0.001);
    opacity: 0;
  }
  100% {
    transform: scale(0.001, 0.001);
    opacity: 1;
  }
}

</style>
