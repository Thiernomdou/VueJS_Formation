<template>
  <div>
      <h1 class="titre">{{  titre }}</h1>
      <liste :myArr="myArr" :txt="txt" v-on:changeTitre="changementTitre($event)"></liste>
  </div>
</template>

<script>
import Liste from './Liste/Liste'
export default {
    name: 'Contenu',
    data() {
        return {
            myArr: [
                {titre: 'Avatar', date: '2005'},
                {titre: 'Prison Break', date: '1994'},
                {titre: 'Tarzan', date: '1990'}
            ],
            txt: 'Hello world',
            titre: 'Je suis le titre'
        }
    },
    components: {
        'liste': Liste
    },
    methods: {
        changementTitre(nouveauTitre) {
            this.titre = nouveauTitre;
        }
    }
}
</script>

<style scoped>
.titre {
    margin-top: 100px!important;
}
</style>