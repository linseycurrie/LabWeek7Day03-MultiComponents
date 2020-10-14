<template>
  <div>
      <label>Search for a character</label>
      <input type="text" v-on:keyup="searchCharacterList">
  </div>
</template>

<script>
export default {
    name:"character-search",
    props:['selectedSearch', 'characters'],
    foundCharacter: "",

    computed: {
        searchCharacterList(){
            
        }
    }

    
}

</script>

<style>

</style>