<template>
  <div id="app" class="container ">
    <h1 class="fs-4 fw-bold">{{ title }}</h1>
    <p>Click to change your team</p>
    <div class="row mx-auto">
      <TheCharacter 
      :id='id' 
      v-for="(id, index) in initial_ids"
      :key="index"
      />

    </div>
  </div>
</template>

<script>
import TheCharacter from './components/TheCharacter.vue'
export default {
  name: 'App',
  components: {
    TheCharacter
  },
  data() {
    return {
      title: 'Generate your team',
      initial_ids: [1, 13, 14]
    }
  },
  methods: {
   
  }
}
</script>

<style>

</style>