<template>
<div>
  <li>{{character.name}}</li>
  <li>{{character.species}}</li>
  <li>{{character.status}}</li> 
</div>
</template>

<script>
export default {
    name: 'character-detail',
    props: ['character']
    
}
</script>

<style>

</style>