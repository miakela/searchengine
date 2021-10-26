<template>
  <div id="app">
    <img id="logo" alt="Vue logo" src="./assets/logo.png">
    <h1>Pokedex</h1>
    <SearchBar v-model="searchQuery" @submit="onSubmit"/>
    <Pokemon/>
    <b-container>
      <PokemonCard :number=searchResults.pokedex_number :content=searchResults.name />
    </b-container>
  </div>
</template>

<script>
import SearchBar from './components/Searchbar.vue';
import PokemonCard from "@/components/PokemonCard";

import axios from 'axios';
import Pokemon from "@/components/Pokemon";


export default {
  name: 'App',
  components: {
    Pokemon,
    SearchBar: SearchBar,
    PokemonCard: PokemonCard,
  },

  data() {
    return {
      searchQuery: '',
      searchResults: [],
    }
  },

  methods: {
    onSubmit() {
      let url;
      if (this.searchQuery === String) {
        url = 'http://ec2-user@ec2-3-90-162-221.compute-1.amazonaws.com:8080/api/pokemon/searchName/'
      } else {
        url = 'http://ec2-user@ec2-3-90-162-221.compute-1.amazonaws.com:8080/api/pokemon/searchID/'
      }
      axios.get(url + this.searchQuery)
          .then((response) => {
            if (response.data === null) {
              this.searchResults = [];
            } else {
              this.searchResults = response.data;
              console.log(this.searchResults)
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

#card {
  padding: 40px !important;
}
</style>
