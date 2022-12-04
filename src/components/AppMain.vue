<script>
import { store } from '../store'
import AppCard from './AppCard.vue'

export default {
    name: 'AppMain',
    components: {
        AppCard,
    },
    data() {
        return {
            store,
        }
    }
}
</script>

<template>
    <main>
        <div class="container">
            <h2>MOVIES:</h2>
            <section>
                <AppCard v-for="movie in store.movies" :info="movie"/>
            </section>
            <h2>SERIES:</h2>
            <section>                
                <AppCard v-for="serie in store.series" :info="serie"/>
            </section>
        </div>
    </main>
</template>

<style lang="scss" scoped>
main {
    background-color: #ddd;
    .container {
    margin:  auto;
    max-width: 75rem;
        section {
            display: flex;
            flex-wrap: wrap;
        }
    }
}
</style>