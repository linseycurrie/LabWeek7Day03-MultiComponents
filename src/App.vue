<template>
  <div id="app">
    <h1>Characters</h1>
    <div>
      
      <character-search :selectedCharacter="selectedCharacter" :characters="characters"></character-search>
      <select v-model="selectedCharacter">
        <option value="" disabled>Selected Character</option>
        <option v-for="(character, index) in characters" :key="index" :value="character">{{character.name}}</option>
      </select>

      <!-- <character-list :characters="characters"></character-list> -->
      <character-detail :selectedCharacter="selectedCharacter"></character-detail>
      
    </div>
  </div>
</template>

<script>
import CharacterDetail from './components/CharacterDetail.vue'
import {eventBus} from './main.js'
import CharacterList from './components/CharacterList.vue'
import CharacterSearch from './components/CharacterSearch.vue'

export default {
  name: 'App',
  data(){
    return {
      characters: [],
      selectedCharacter: null,
      foundCharacter: ""
    }
  },

  mounted(){
    fetch('https://rickandmortyapi.com/api/character/')
    .then(response => response.json())
    .then(data => this.characters = data.results)


    eventBus.$on('character-selected', (character) => {
      this.selectedCharacter = character;
    })

    // console.log(this.characterNames);
  },

  computed: {
    
    
  },


  components: {
    "character-list": CharacterList,
    "character-detail": CharacterDetail,
    "character-search": CharacterSearch,
  },

  
    
}

  

// }
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
</style>
