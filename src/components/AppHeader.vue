<script>
export default {
    name: 'AppHeader'
}
</script>

<template>
<header>
    <div class="container">
        <h1>BOOLFLIX</h1>
        <form>
            <input type="text" placeholder="Inserisci testo">
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
    }
}

</style>
