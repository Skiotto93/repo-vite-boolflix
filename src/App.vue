<script>
import AppHeader from './components/AppHeader.vue';
import AppMain from './components/AppMain.vue';
import axios from 'axios';
import { store } from './store';
import AppError from './components/AppError.vue';

export default {
    components: {
        AppHeader,
        AppMain,
        AppError,
    },
    data() {
        return {
            store,
            error: false,
        }
    },
    methods: {
        getResult() {
            axios.get('https://api.themoviedb.org/3/search/movie', {
                params: {
                    api_key:'b1135ad7d7c335cd655ce87e2c1b8cca',
                    query: store.textResearch,
                    language: 'it-IT',
                }
            }).then((response) => {
                console.log(response);
                this.store.movies = response.data.results;
                if(!this.error) {
                    this.error = !this.error;
                }
            }).catch((err) => {
                this.error = true;
            });
            // ricerca serie tv
            axios.get('https://api.themoviedb.org/3/search/tv', {
                params: {
                    api_key:'b1135ad7d7c335cd655ce87e2c1b8cca',
                    query: store.textResearch,
                    language: 'it-IT',
                }
            }).then((response) => {
                console.log(response);
                this.store.series = response.data.results;
                if(!this.error) {
                    this.error = !this.error;
                }
            }).catch((err) => {
                this.error = true;
            });
        },
    }
}
</script>

<template>
    <AppHeader @performSearch="getResult"/>
    <AppMain/>
    <AppError v-if="error"/>
</template>

<style scoped>

</style>
