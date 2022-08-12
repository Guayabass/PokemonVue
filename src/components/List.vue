<template >
    <div class="container">

        <div class="card" v-for="pokemon of pokemons">
            <img class="pokemon__image"
                :src="getImageUrl(pokemon.url)"
                :alt="pokemon.name">
            <h3>Pokemon: {{ pokemon.name }}</h3>
        </div>
    </div>

</template>

<script>
import axios from "axios";
export default {
    name: "List",
    data() {
        return {
            pokemons: null
        }
    },
    created() {
        axios.get('https://pokeapi.co/api/v2/pokemon?offset=0&limit=10')
            .then(response => (this.pokemons = response.data.results))
    },
    methods: {
        getImageUrl(pokemonUrl) {
            let imageUrl = 'https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/ID.png'
            let idParameter = pokemonUrl.match(/\d+/g);
            return imageUrl.replace('ID', idParameter[1])
        }
    }
}
</script>

<style scoped>
.container {
    width: 100%;
    max-width: 1200px;
    margin: 0 auto;
    padding: 15px;
    color: white;
    display: flex;
    flex-wrap: wrap;
    justify-content: space-between;
}

.card {
    width: 300px;
    height: 500px;
    padding: 5px;
    margin: 20px;
    border: white solid 1px;
    display: flex;
    align-items: center;
    justify-content: center;
    flex-direction: column;
}

.pokemon__image {
    width: 250px;
    height: 250px;
    display: block;
}
</style>