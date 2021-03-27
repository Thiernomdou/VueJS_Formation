<template>
<div>

    <ul class="liste mt-5">
        <!-- Toujours dans une boucle for, récupérer
        l'index aussi et faire un v-bind de l'index
        pour donner là à chaque li une clé unique -->
        <li v-for="(film, index) in myArr" v-bind:key="index">
            <div class="card">
                <div class="card-body">
                    Titre : {{ film.titre }}
                    <br>
                    Date : {{ film.date }}
                </div>
            </div>
        </li>
    </ul>
    
    <p>{{ txt }}</p>

    <div v-on:click="supprFilm" class="btn btn-danger mt-2">Supprime le film</div>
    <div v-on:click="supprTxt" class="btn btn-danger mt-2 ml-2">Supprime le texte</div>
    <div v-on:click="changeTitre" class="btn btn-danger mt-2 ml-2">Modifie le titre</div>

    <slot>Patientez</slot>
    <slot name="info"></slot>
</div>
</template>

<script>

    import {bus} from '../../main'

    export default {
        name:'Liste',
        data() {
            return {
                fruits: ['Orange', 'Papaye', 'Fraise']
            }
        },
        methods: {
            supprFilm: function() {
                this.myArr.pop();
            },
            supprTxt: function() {
                this.txt = "";
            },
            changeTitre: function() {
                //this.$emit('changeTitre', 'Mon nouveau Titre')
                bus.$emit('changeTitre', 'Titre changé avec le bus')
            }
        },
        //Les props (propriétés)
        //pour passer des props d'un parent à un enfant,
        //il faut aller sur le composant qui va recevoir les props
        //donc l'enfant et lui dire tu vas recevoir des props avec 
        //la propriété props avec le nom des props
        props: ['myArr', 'txt']
        
    }
</script>

<style scoped src="./Liste.css">

ul {
    background: orange;
}
p {
    color: red;
}
</style>