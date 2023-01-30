<script>
import axios from 'axios';
export default {
    name: 'SelectForm',
    data() {
        return {
            types: [],
            type: '',
            apiUriType: 'https://41tyokboji.execute-api.eu-central-1.amazonaws.com/dev/api/v1/pokemons/types1'
        }
    },
    emits: ['option-change'],
    methods: {
        fetchPokemonType(url) {
            axios.get(url).then((res) => {
                this.types = res.data;
            });
        }
    },
    created() {
        this.fetchPokemonType(this.apiUriType);
    }
}
</script>


<template>
    <div class="m-5">
        <select name="select" v-model="type" @change="$emit('option-change', type)">
            <option v-for="type in types">{{ type }}</option>
        </select>
    </div>
</template>

<style>

</style>