<template>
    <ul>
        <character-item v-for="(character, index) in characters" :character="character" :key="index"></character-item>
    </ul>
</template>

<script>
import CharacterItem from './CharacterItem.vue'

export default {
    name: "characters-list",
    props:['characters'],

    components: {
        'character-item': CharacterItem,
    }

}


</script>

<style>

</style>