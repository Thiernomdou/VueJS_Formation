<template>
    <div class="container mt-5">
        <!-- <h1>{{ titre }}</h1>

        <div class="btn btn-outline-primary mr-2 mb-2" v-on:click="component = 'texte1'">Onglet 1</div>
        <div class="btn btn-outline-primary mb-2" v-on:click="component = 'texte2'">Onglet 2</div>
            
        <div class="onglets card mb-5" >
            <component class="p-5" :is="component"></component>
        </div>

        <modale :revele="revele" :toggleModale="toggleModale"></modale>

        <div v-on:click="toggleModale" class="btn btn-success">Ouvre la modale</div> -->
        
        <!-- <h1>Appel à une API</h1>
        <img :src="urlImg" alt="image"> -->

        <h1>Formulaire</h1>
        <form>

            <div class="form-group">
                <label for="prenom">Ton prénom</label>
                <input v-model="formData.prenom" type="text" id="prenom" class="form-control">
            </div>

            <div class="form-group">
                <label for="text">Ton texte</label>
                <textarea v-model="formData.text" id="text" class="form-control"></textarea>
            </div>

            <h2>Résultats</h2>

            <div class="card p-3">
                <p>Prénom : {{ formData.prenom }}</p>
                <p style="white-space: pre">Texte : {{ formData.text }}</p>
            </div>
    
        </form>
        
    </div>
</template>

<script>


// import Texte1 from './Texte1'
// import Texte2 from './Texte2'
// import Modale from './Modale'

// import axios from 'axios'

export default {
    name: 'Contenu',
    data() {
        return {
            // myArr: [
            //     {titre: 'Inception', date: 2010},
            //     {titre: 'Avatar', date: 2009},
            //     {titre: 'Seven', date: 1995}
            // ],
            // txt: 'Hello World',
            // titre: 'Je suis le titre',
            // toggle1: true,
            // toggle2: false,
            // component: 'texte1',
            // revele: false
            // urlImg : null

            formData : {
                prenom : '',
                text: ''
            }
        }
    },
    methods: {
    //    toggleOng1: function() {
    //        this.toggle1 = true,
    //        this.toggle2 = false
    //    },
    //    toggleOng2: function() {
    //        this.toggle1 = false,
    //        this.toggle2 = true
    //    },
    //    toggleModale: function() {
    //        this.revele = !this.revele
    //    }
    },
    // Quand le composant sera bien affiché
    // mounted() {
    //     axios
    //     .get('https://api.thecatapi.com/v1/images/search')
    //     .then(reponse => {
    //         console.log(reponse);
    //         this.urlImg = reponse.data[0].url
    //     })
    // },
    components: {
    //    'texte1': Texte1,
    //    'texte2': Texte2,
    //    'modale': Modale
    }
}

</script>

<style scoped>

    h1 {
        margin-top: 100px!important;
    }
    .onglets {
        height: 200px;
    }
</style>