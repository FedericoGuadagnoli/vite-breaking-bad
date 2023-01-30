<script>
export default {
    name: 'PokemonCard',
    props: {
        image: String,
        name: String,
        number: Number,
        type: String
    },
    computed: {
        bgClass() {
            if (this.type === 'Grass') return 'green'
            if (this.type === 'Water') return 'blue'
            if (this.type === 'Fire') return 'red'
            if (this.type === 'Normal') return 'yellow'
            if (this.type === 'Dark') return 'dark'
        }
    }
}
</script>


<template>
    <div class="card m-0 d-flex flex-column align-items-center justify-content-center rounded " :class="bgClass">
        <img class="img-fluid h-50" :src="image" alt="name">
        <span class="number fs-3">{{ number }}</span>
        <div class="name h1">{{ name }}</div>
        <div class="type fs-2">{{ type }}</div>
    </div>
</template>

<style scoped lang="scss">
@use '../../assets/scss/partials/variables.scss' as *;

.card {
    flex-basis: calc(25% - 1rem);
    height: 20rem;
    border: 2px solid pink;
}

.green {
    background-color: $bg-green;
}

.blue {
    background-color: $bg-violet;
}

.red {
    background-color: $bg-red;
}

.yellow {
    background-color: $bg-yellow;
}

.dark {
    background-color: $bg-black;
    color: white;
}
</style>