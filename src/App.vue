<template>
  <div id="app">
    <img id="logo" alt="Vue logo" src="./assets/logo.png">
    <h1>Pokedex</h1>
    <SearchBar v-model="searchQuery" @submit="onSubmit" />

    <b-container>
      <template v-if="searchResults.length > 0">
        <PokemonCard
            v-for="(item, index) in searchResults"
            :key="`resultCard-${index}`"
            :number="index + 1"
            :content="item"
        />
      </template>

      <template v-else>
        <div class="text-secondary text-center">Keine Ergebnisse!</div>
      </template>
    </b-container>

  </div>
</template>

<script>
import SearchBar from './components/Searchbar.vue';
import PokemonCard from "@/components/PokemonCard";

import axios from "axios";

export default {
  name: 'App',
  components: {
    SearchBar: SearchBar,
    PokemonCard: PokemonCard
  },

  data() {
    return {
      searchQuery: '',
      searchResults: []
    }
  },

  methods: {
    onsubmit() {
      axios.get(
          'http://ec2-54-227-29-253.compute-1.amazonaws.com:8080/api/pokemon/searchName/',
          {
            params: {
              query: this.searchQuery
            },
          }
      )
      .then((response) => {
        if (response.data === null) {
          this.searchResults = [];
        } else {
          this.searchResults = response.data;
        }
      })
      .catch((error) => {
        console.log(error);
        this.searchResults = []
          })
    }
  }
}

</script>

<style>
html {
  background-color: #19191B;
}
#app {
  font-family: "Open Sans", sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #eeeeee;
  margin-top: 60px;
  background-color: #19191B;
}
#logo {
  width: 40%;
}
#card{
  padding: 40px !important;
}
</style>
