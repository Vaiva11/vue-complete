<template>
  <div class="card">
    <img v-bind:src="image">
    <div class='text'>
        {{ name }} 
        <div v-if="yearOfBirth">
          {{ 2021 - yearOfBirth }}
        </div>
    </div>
    <router-link :to="{ name: 'Profile', params: {
        name: name,
        house: house,
        species: species,
        gender: gender,
        house: house,
        wand: wand,
        image: image
      }}">
      See profile
    </router-link>
  </div>
</template>

<script>
export default {
  name: 'Card',
  props: {
    image: String,
    name: String,
    yearOfBirth: Number,
    species: String,
    gender: String,
    house: String,
    wand: {
      wood: String,
      core: String,
      length: Number
    }
  }
}
</script>

<style scoped>
.card{
    border: solid gray 1px;
    border-radius: 10px;
    width: 300px;
    height: 400px;
    display: flex;
    text-align: center;
    align-items: center;
    flex-direction: column;
    padding: 20px 10px;
    box-shadow: 10px 10px 10px 10px;
    margin: 20px;
}
img {
  height: 250px;
}
.text {
    font-size: 30px;
    font-weight: bold;
    margin-top: 60px;
}
</style>
