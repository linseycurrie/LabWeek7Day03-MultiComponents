<template>
  <div v-if="selectedCharacter">
      <h3>{{selectedCharacter.name}}</h3>
      <p>Species: {{selectedCharacter.species}}</p>
      <p>Status: {{selectedCharacter.status}}</p>
      <img  :src="selectedCharacter.image">
      <p>Origin: {{selectedCharacter.origin.name}}</p>

  </div>
</template>

<script>
export default {
    name: 'character-detail',
    props: ['selectedCharacter']

}
</script>

<style>

</style>