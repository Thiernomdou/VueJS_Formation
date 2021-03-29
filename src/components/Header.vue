<template>
    <div class="header-top">
        <p>{{ titre }}</p>
    </div>
</template>

<script>
    import {bus} from '../main'

    export default {
        name: 'Header',
        data() {
            return {
                titre: 'La To-Do Liste'
            }
        },
        //on les utilise si on veut intervenir
        //à des moments précis de la vie d'un composant
        //on peut utiliser ces méthodes
        beforeCreate() {
            console.log('Il va être crée')
        },
        //Quand le composant est crée, alors
        //on passe à l'écoute de l'évènement
        created() {
            console.log('Le composant est crée')
            bus.$on('changeTitre', (data) => {
                this.titre = data
            })
        },
        beforeMount() {
            console.log("Il va être monté dans le DOM");
        },
        mounted() {
            console.log("Il est integré dans le DOM");
        },
        beforeUpdate() {
            console.log("Il va se mettre à jour");
        },
        updated() {
            console.log("Le composant s'est mis à jour");
        }
    }
</script>

<style scoped>
    .header-top {
        position: fixed;
        top: 0;
        height: 50px;
        background: #333;
        color: #f1f1f1;
        width: 100%;
        text-align: center;
        line-height: 50px;
        font-size: 25px;
    }
</style>