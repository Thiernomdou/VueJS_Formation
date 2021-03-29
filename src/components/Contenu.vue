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

        <!-- <h1>Formulaire</h1> -->
        <!-- <form>

            <div class="form-group">
                <label for="prenom">Ton prénom</label>
                <input v-on:input="toggleResult" v-model="formData.prenom" type="text" id="prenom" class="form-control">
            </div>

            <div class="form-group">
                <label for="text">Ton texte</label>
                <textarea v-model="formData.text" id="text" class="form-control"></textarea>
            </div> -->

            <!-- Select Box -->
            <!-- <h3>Select Box</h3>
            <select v-model="formData.select">
                <option v-for="(pays, index) in formData.listePays" :key="index">{{ pays }}</option>
            </select> -->

            <!-- Les checkbox -->
            <!-- <h3 class="mt-3">CheckBoxs</h3>
            <div class="form-check">
                <input v-model="formData.checkFruits" type="checkbox" id="fraise" class="form-check-input" value="fraise">
                <label for="fraise">Fraise</label>
            </div>

            <div class="form-check">
                <input v-model="formData.checkFruits" type="checkbox" id="pomme" class="form-check-input" value="pomme">
                <label for="pomme">Pomme</label>
            </div>

            <div class="form-check">
                <input v-model="formData.checkFruits" type="checkbox" id="cerises" class="form-check-input" value="cerises">
                <label for="cerises">Cerises</label>
            </div>


            
            <button v-on:click.prevent="envoiForm" class="btn btn-primary mt-3 mb-3">Envoyez les données</button>

            <div v-if="infoSubmit">
                <h2>Résultats</h2>

                <div class="card p-3">
                    <p>Prénom : {{ formData.prenom }}</p>
                    <p style="white-space: pre">Texte : {{ formData.text }}</p>
                
                    <p>Résultats checkboxs</p>
                    <ul>
                        <li v-for="(fruit, index) in formData.checkFruits" :key="index">{{ fruit }}</li>
                    </ul>

                    <p>Choisissez un pays : {{ formData.select }}</p>
                
                </div>

            </div>
            

        </form> -->

        <h1>Rentrer des choses à faire</h1>
        <form>

            <div class="form-group">
                <label for="action">Action</label>
                <input v-model="formData.tache" type="text" id="action" class="form-control">
            </div>

            <button v-on:click.prevent="creationItem" class="btn btn-primary mt-2 mb-3">Créer une tâche</button>

        </form>

        <ul>
            <li v-for="(tache, index) in tableauTaches" :key="index">
                <item :tache="tache" :id="index" :suppression="suppression"></item>
            </li>
        </ul>
        
    </div>
</template>


<script>

import Item from './Item'

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

            // formData: {
            //     prenom: '',
            //     text: '',
            //     checkFruits: [],
            //     select: '',
            //     listePays: ['France', 'Guinée', 'Canada', 'Etats-Unis']
            // },
            // infoSubmit: false

            //to-doliste
            formData: {
                tache: ''
            },
            tableauTaches: ['JavaScript', 'Vue', 'Python', 'React', 'Angular']
            
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

        // envoiForm: function() {
        //     this.infoSubmit = true;
        // },
        // toggleResult: function() {
        //     this.infoSubmit = false;
        // }

        creationItem: function() {
            this.tableauTaches.push(this.formData.tache);
            this.formData.tache = '';
        },
        suppression: function() {
            this.tableauTaches.splice(e.target.parentNode.id, 1)
        }
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
    'item': Item
    }
}

</script>

<style scoped>

    h1 {
        margin-top: 100px!important;
    }
    ul {
    list-style-type: none;
    padding: 0;
}
    /* .onglets {
        height: 200px;
    } */
</style>