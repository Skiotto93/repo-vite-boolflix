<script>
import CountryFlag from 'vue-country-flag-next';

export default {
    name: 'AppCard',
    props: {
        info: Object,
    },
    components: {
        CountryFlag,
    },
    methods: {
        getFlag(lang) {
            if( lang === 'en') {
                return 'gb'
            } else if ( lang === 'it' ) {
                return 'it'
            } else if ( lang === 'fr' ) {
                return 'fr'
            } else if ( lang === 'jp' ) {
                return 'jp'
            } else if ( lang === 'sp' ) {
                return 'sp'
            } else if ( lang === 'hi' ) {
                return 'in'
            } else if ( lang === 'sv' ) {
                return 'se'
            }
            return lang;
        }
    },
    computed: {
        vote() {
            return Math.ceil(this.info.vote_average / 2);
        },
        imgCard() {
            return this.info.poster_path 
            ? `https://image.tmdb.org/t/p/w342${this.info.poster_path}` 
            : `https://via.placeholder.com/342x510.png?text=No+Image+Found`
        }
    },
}
</script>

<template>
        <div class="card">
            <img :src="imgCard" :alt="title">
            <h3>{{ info.title }} {{ info.name }}</h3>
            <span><strong>Titolo originale: </strong>{{ info.original_title }} {{ info.original_name }}</span>
            <div><strong>Lingua: </strong> <country-flag :country='getFlag(info.original_language)' size='small' /></div>
            <div>
                <strong>Voto: </strong>
                <font-awesome-icon 
                v-for="n in vote"
                class="starFull"
                icon="fa-solid fa-star" />
                <font-awesome-icon 
                v-for="n in 5 - vote"
                class="starEmpty" 
                icon="fa-regular fa-star" />
            </div>
        </div>
</template>

<style lang="scss" scoped>
.card {
    padding: 10px 0;
    .starFull {
        color: gold;
    }
    .starEmpty {
        color: grey;
    }
}
</style>