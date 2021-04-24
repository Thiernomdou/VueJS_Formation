<template>
  <div>
      <ul class="liste mt-3">
          <li  v-for="(film, index) in myArr" :key="index">
              <div class="card">
                  <div class="card-body">
                    Titre : {{ film.titre }}
                    <br>
                    Date : {{ film.date }}
                    <br>
                  </div>
              </div>
              </li>
      </ul>
      <p>{{ txt }}</p>
      <button @click="supprFilm" class="btn btn-danger mt-3 mr-5">Supprimer le fiml</button>
      <button @click="supprText" class="btn btn-danger mt-3 mr-5">Supprimer le texte</button>
      <button @click="changeTitre" class="btn btn-danger mt-3 mr-5">Modifier le titre</button>
      <button @click="changeTitreBus" class="btn btn-danger mt-3">Modifier le header</button>
  </div>
</template>

<script>
import {bus} from '../../main'
export default {
    name: 'Liste',
    data() {
        return {
            // fruits: ['Orange', 'papaye', 'Fraise']
        }
    }, 
    props: ['myArr', 'txt'],
    methods: {
        supprFilm() {
            this.myArr.pop();
        },
        supprText() {
            this.txt = ""
        },
        changeTitre() {
            // $emit sert à créer un évènement personnalisé auquel 
            // le composant parent peut écouter
            this.$emit('changeTitre', 'Mon nouveau titre')
        },
        changeTitreBus() {
            // $emit sert à créer un évènement personnalisé auquel 
            // le composant parent peut écouter
            //bus permet de communiquer avec composant
            //qui se situe hors de sa liaison
            bus.$emit('changeTitreBus', 'Titre changé avec le bus')
        }
    }

}
</script>

<style src="./Liste.css" scoped>
ul {
    list-style-type: none;
    padding: 0;
}
</style>