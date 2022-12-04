<script>
import { store } from '../store'

export default {
    name: 'AppHeader',
    data() {
        return {
            store,
        }
    }
}
</script>

<template>
<header>
    <div class="container">
        <h1>BOOLFLIX</h1>
        <form  @submit.prevent="$emit('performSearch')">
            <input class="textSearch" type="text" 
            placeholder="Inserisci testo" v-model="store.textResearch"
            required>
            <button class="btn" type="submit">
                Search
            </button>
        </form>
    </div>
</header>
</template>

<style lang="scss" scoped>
header {
    background-color: #000;
    padding: 1.25rem;
    
    .container {
    margin:  auto;
    max-width: 75rem;
    display: flex;
    justify-content: space-between;
    align-items: center;
    h1 {
        color: red;
    }
    .textSearch {
        padding: 5px 10px;
        border-radius: 5px;
    }
    .btn {
        padding: 5px;
        border: none;
        border-radius: 5px;
        margin-left: 10px;
        cursor: pointer;
    }
    }
}

</style>
