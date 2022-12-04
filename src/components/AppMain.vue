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
            <AppCard v-for="movie in store.movies" :info="movie"/>
            <AppCard v-for="serie in store.series" :info="serie"/>
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