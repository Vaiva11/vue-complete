<template>
  <div id="app" class="cards">
    <div v-for="card in info" v-bind:key="card.name">
      <Card
        :name="card.name"
        :image="card.image"
        :yearOfBirth="card.yearOfBirth"
        :species="card.species"
        :gender="card.gender"
        :house="card.house"
        :wand="card.wand"
      />
    </div>
  </div>
</template>

<script>
import Card from '../components/Card.vue'
import axios from 'axios'

export default {
  name: 'Home',
  components: {
    Card
  },
  data () {
    return {
      info: null
    }
  },
  mounted () {
    axios
      .get('http://hp-api.herokuapp.com/api/characters')
      .then(response => (this.info = response.data))
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
.cards{
  display: flex;
  justify-content: center;
  flex-wrap: wrap;
}
</style>
