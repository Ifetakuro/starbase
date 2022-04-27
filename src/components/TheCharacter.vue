<template>
  <div class="col-md-4 mt-5" @click="switchCharacter">
    <div class="character-card">
      <div class="card-block p-3">
        <h4 class="card-title">{{ characters.name }}</h4>
        <p class="card-text">Height: {{ characters.height }}</p>
        <p class="card-text">Mass: {{ characters.mass }}kg</p>
        <p class="card-text">Hair Color: {{ characters.hair_color }}</p>
        <p class="card-text">Eye Color: {{ characters.eye_color }}</p>

      </div>
    </div>
  </div>
</template>

<script>
export default {
 name: 'TheCharacter',
 props: {
   'id': Number,
 },
 data() {
   return {
     characters: {}
   }
 },
 methods: {
    fetchCharacter(id) {
      fetch(`https://swapi.dev/api/people/${id}`, {
        method: 'GET'
      }).then(response => response.json())
        .then(result => this.characters = result)
    },
    switchCharacter() {
      let randomId = Math.floor(Math.random() * 83) + 1;
      this.fetchCharacter(randomId)
    }
  },
  created() {
    this.fetchCharacter(this.id)
  }
}
</script>

<style>

</style>