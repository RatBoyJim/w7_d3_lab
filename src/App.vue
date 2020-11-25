<template>
<div class="main-container">
  <characters-list :characters='characters'></characters-list>
  <character-detail v-if="selectedCharacter" :character='selectedCharacter'></character-detail>
</div>
</template>

<script>
  import CharacterList from './components/CharacterList.vue';
  import CharacterDetail from './components/CharacterDetail.vue';
  import {eventBus} from './main.js'
export default {
  name: 'app',
  data(){
    return {
      characters: [],
      selectedCharacter: null
    }
  },
  mounted(){
    fetch("https://rickandmortyapi.com/api/character/")
    .then(res => res.json())
    .then(characters => this.characters = characters.results)
    eventBus.$on('character-selected', (character) => { this.selectedCharacter = character; })
    },
  components: {
    "characters-list": CharacterList,
    "character-detail": CharacterDetail
  }

}
</script>

<style>
.main-container {
    display: flex;
    justify-content: space-between;
  }

</style>