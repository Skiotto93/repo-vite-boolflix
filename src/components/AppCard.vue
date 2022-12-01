<script>
export default {
    name: 'AppCard',
    props: {
        info: Object,
    },
}
</script>

<template>
        <div class="card">
            <h3>{{ info.title }}</h3>
            <span>{{ info.original_title }}</span>
            <div>{{ info.original_language }}</div>
            <div>{{ info.vote_average }}</div>
        </div>
</template>

<style lang="scss" scoped>

</style>