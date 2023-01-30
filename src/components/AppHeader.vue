<script>
export default {
    name: 'AppHeader'
}
</script>


<template>
    <header>
        <div class="container-fluid mt-5">
            <div class="d-flex justify-content-between">
                <div class="circle-container d-flex">
                    <div class="big circle"></div>
                    <div class="small circle"></div>
                    <div class="small circle"></div>
                    <div class="small circle"></div>
                </div>
                <figure>
                    <img src="../assets/img/pokemon.png" alt="pokemon">
                </figure>
            </div>
        </div>
    </header>
</template>


<style scoped lang="scss">
@use '../assets/scss/partials/variables.scss' as *;

.circle {
    margin: 0 1rem;
    width: 50px;
    height: 50px;
    background-color: $bg-violet;
    border-radius: 50%;
    border: 2px solid white;
}

.big {
    width: 100px;
    height: 100px;
}

.circle:nth-child(2) {
    background-color: $bg-red;
}

.circle:nth-child(3) {
    background-color: $bg-yellow;
}

.circle:nth-child(4) {
    background-color: $bg-green;
}

figure {
    img {
        width: 20rem;
    }
}
</style>