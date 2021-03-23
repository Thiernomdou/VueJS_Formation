<template>
    <div>
        <p>
        {{ txt }}
        </p>
    <liste :prenom="prenom"></liste>
    </div>
</template>

<script>


import Liste from './Liste/Liste.vue'

export default {
    name: 'Contenu',
    data() {
        return {
            txt : 'Je suis le contenu',
            prenom : function() {
                console.log("Hello depuis le parent")
            }
        }
    },
    components: {
        'liste': Liste
    }
}

</script>

<style>

</style>