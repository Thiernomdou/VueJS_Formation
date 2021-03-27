<template>
  <div id="app">
    <contenu></contenu>
    <header-top></header-top>
  </div>
</template>

<script>

import Contenu from './components/Contenu.vue'
import Header from './components/Header.vue'


export default {
  name: 'App',
  //la propriété components qui permet
  //d'enregistrer les composants localement
  components: {
    'contenu': Contenu,
    'header-top' : Header
  }
}
</script>

<style>
</style>
