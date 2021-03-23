<template>
  <div id="app">
    <img alt="Vue logo" src="./assets/logo.png">
    <contenu></contenu>
  </div>
</template>

<script>

import Contenu from './components/Contenu.vue'

export default {
  name: 'App',
  //la propriété components qui permet
  //d'enregistrer les composants localement
  components: {
    'contenu': Contenu
  }
}
</script>

<style>
</style>
