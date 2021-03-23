<template>
<div>
    <ul class="liste">
        <!-- Toujours dans une boucle for, récupérer
        l'index aussi et faire un v-bind de l'index
        pour donner là à chaque li une clé unique -->
        <li v-for="(fruit, index) in fruits" v-bind:key="index">{{ fruit }}</li>
    </ul>

    <p> {{ prenom() }}</p>

</div>
</template>

<script>
    export default {
        name:'Liste',
        data() {
            return {
                fruits: ['Orange', 'Papaye', 'Fraise']
            }
        },
        //Les props (propriétés)
        //pour passer des props d'un parent à un enfant,
        //il faut aller sur le composant qui va recevoir les props
        //donc l'enfant et lui dire tu vas recevoir des props avec 
        //la propriété props avec le nom des props
        props: {
            prenom: {
                // le type de la props qu'on attends de recevoir
                // de la part du composant parent
                type: Function
            }
        }
        
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