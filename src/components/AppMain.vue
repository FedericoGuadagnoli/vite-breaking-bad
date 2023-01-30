<script>
import { store } from '../data/store';
import PokemonCard from './pokemons/PokemonCard.vue';
import AppLoader from './AppLoader.vue';
export default {
    name: 'AppMain',
    components: { PokemonCard, AppLoader },
    data() {
        return {
            store
        }
    }
}
</script>


<template>
    <app-loader v-if="store.isLoading"></app-loader>
    <main v-else>
        <div class="container-fluid  p-5">
            <div class="row d-flex flex-wrap align-content-start g-1 gap-3 p-5">
                <PokemonCard v-for="pokemon in store.pokemons" :key="pokemon.id" :image="pokemon.image"
                    :name="pokemon.name" :number="pokemon.number" :type="pokemon.type">
                </PokemonCard>
            </div>

        </div>
    </main>
</template>

<style scoped lang="scss">
@use '../assets/scss/partials/variables.scss' as *;

.container-fluid {
    background-color: $bg-lightgrey;

    .row {
        background-color: $bg-black;
        overflow-y: scroll;
        height: 50rem;
    }


}
</style>