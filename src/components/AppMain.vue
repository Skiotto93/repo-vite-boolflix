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
            <section>
                <h2>Movies:</h2>
                <AppCard v-for="movie in store.movies" :info="movie"/>
            </section>
            <section>
                <h2>Series:</h2>
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
    // display: flex;
    }
}
</style>