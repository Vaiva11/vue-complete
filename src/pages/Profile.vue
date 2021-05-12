<template>
  <div class="page">
    <div class="profile">
      <div class="text">
        <h2>{{profileData.name}}</h2>
        <p>Species: {{profileData.species}}</p>
        <p>Gender: {{profileData.gender}}</p>
        <p>House: {{profileData.house}}</p>
        <p>Wand: {{profileData.wand.wood}}, {{profileData.wand.core}}, {{profileData.wand.length}}"</p>
        <button v-on:click="$router.go(-1)"> Back</button>
      </div>
      <img v-bind:src="profileData.image">
    </div>
  </div>
</template>
<script>
export default {
  name: 'Profile',
  data () {
    return {
      profileData: null
    }
  },
  created() {
    this.profileData = this.$route.params;
  },
}
</script>

<style scoped>
.page{
  width: 100%;
  display: flex;
  align-items: center;
  justify-content: center;
}
.profile {
  display: flex;
  margin-top: 100px;
  padding: 50px;
  max-width: 50%;
  border: solid gray 1px;
  box-shadow: 10px 10px 10px 10px;
  border-radius: 10px;
  background: aliceblue;
}
img {
  margin-left: 25px;
  height: 250px;
  border-radius: 15px;
}
p {
  font-size: 20px;
}
button {
  border: solid gray 1px;
  border-radius: 10px;
  background: aliceblue;
  padding: 10px 20px;
  font-size: 16px;
  cursor: pointer;
}
</style>



