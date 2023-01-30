<script>
import axios from 'axios';
import AppHeader from './components/AppHeader.vue';
import AppMain from './components/AppMain.vue';
import SelectForm from './components/SelectForm.vue';
import { store } from './data/store';
export default {
  components: { AppHeader, AppMain, SelectForm },
  data() {
    return {
      store,
      apiUri: 'https://41tyokboji.execute-api.eu-central-1.amazonaws.com/dev/api/v1/pokemons',
      typeFilter: ''
    }
  },
  methods: {
    fetchPokemons(url) {
      store.isLoading = true;
      axios.get(url).then((res) => {
        const apiPokemons = res.data.docs;
        store.pokemons = apiPokemons.map(pokemon => {
          const { name, number, type1, imageUrl } = pokemon;
          return { name, number, type: type1, image: imageUrl };
        })
      }).catch((error) => {
        store.pokemons = [];
      }).then(() => {
        store.isLoading = false;
      });
    },
    onOptionChange(type) {
      this.typeFilter = type;
      this.searchPokemonType();
    },
    searchPokemonType() {
      const url = `${this.apiUri}?eq[type1]=${this.typeFilter}`;
      this.fetchPokemons(url);
    }
  },
  created() {
    this.fetchPokemons(this.apiUri);
  }
}
</script>

<template>
  <app-header></app-header>
  <select-form @option-change="onOptionChange"></select-form>
  <app-main></app-main>
</template>

<style lang="scss">
@use './assets/scss/style.scss' as *;
</style>
