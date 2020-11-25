<template>
<div>
    <list-item v-for="(character, index ) in characters" :character="character" :key="index"> 
    </list-item>
</div>
  
</template>

<script>
import ListItem from './CharacterItem.vue'
export default {

    name: 'characters-list',
    props: ['characters'],
    components: {
        "list-item": ListItem
    }
}
</script>

<style>

</style>