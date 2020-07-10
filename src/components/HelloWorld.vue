<template>
  <v-container>
    <v-btn @click="test">lool</v-btn>
  </v-container>
</template>

<script>
import { CANDIDAT_TOKEN_STORAGE_KEY } from '../constants'
const baseUrlProd = 'https://beta.interieur.gouv.fr/candilib/api/v2/'
const baseUrlQualif = 'https://candilib-qualif.netlify.app/candilib/api/v2/'
const baseUrlLocal = 'http://localhost:8000/api/v2/'
import axios from 'axios'
    
  export default {
    methods: {
      async test() {
        axios.get(`${baseUrlQualif}public/departements`)
          .then(response => {
            console.log(response.data.url);
            console.log(response.data.explanation);
            console.log('baseUrlProd', {response})
          })
          .catch(error => {
            console.log(error)
          })
        // fetch.fetchUrl(`${baseUrlLocal}public/departements`).then(response => {
        //     console.log(response.data.url);
        //     console.log(response.data.explanation);
        //     console.log('baseUrlLocal:', {response})
        //   })
        //   .catch(error => {
        //     console.log(error)
        //   })
            
        // axios.get(`${baseUrlLocal}public/departements`)
        //   .then(response => {
        //     console.log(response.data.url);
        //     console.log(response.data.explanation);
        //     console.log('baseUrlLocal:', {response})
        //   })
        //   .catch(error => {
        //     console.log(error)
        //   })
            
        // axios.get(`https://beta.interieur.gouv.fr/candilib/api/v2/candidat?token=${token}`)
        //   .then(response => {
        //     console.log(response.data.url);
        //     console.log(response.data.explanation);
        //     console.log({response})
        //   })
        //   .catch(error => {
        //     console.log(error)
        //   })
        
      }
    },
  }
</script>
