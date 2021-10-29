<template>
  <div id="app">
    <img id="logo" alt="Vue logo" src="./assets/logo.png">
    <h1>Pokedex</h1>
    <SearchBar v-model="searchQuery" @submit="onSubmit"/>
    <b-container>
      <PokemonCard v-if="searchResults.length === 0" :number=searchResults.pokedex_number :content=searchResults.name />
      <PokemonCard :searchresults=searchResults />
      <Pokemon v-if="searchResults.length !== 0" v-bind:imgsrc="resolveImgSource" :result=searchResults :pokedexNumb=getNumber />
    </b-container>
  </div>
</template>

<script>
import SearchBar from './components/Searchbar.vue';
import PokemonCard from "@/components/PokemonCard";
import Pokemon from "@/components/Pokemon";

import axios from 'axios';

export default {
  name: 'App',

  components: {
    SearchBar: SearchBar,
    Pokemon: Pokemon,
    PokemonCard: PokemonCard,
  },

  data() {
    return {
      searchQuery: '',
      searchResults: [],
    }
  },

  computed: {

    resolveImgSource: function () {
      let imgurl;
      /*this.searchResults.pokedex_number*/
      if ((this.searchResults.pokedex_number) < 10) {
        imgurl = "https://assets.pokemon.com/assets/cms2/img/pokedex/full/00" + this.searchResults.pokedex_number + ".png"
      } else if ((this.searchResults.pokedex_number) < 100) {
        imgurl = "https://assets.pokemon.com/assets/cms2/img/pokedex/full/0" + this.searchResults.pokedex_number + ".png"
      } else if ((this.searchResults.pokedex_number) < 1000) {
        imgurl = "https://assets.pokemon.com/assets/cms2/img/pokedex/full/" + this.searchResults.pokedex_number + ".png"
      } else {
        imgurl = "https://assets.pokemon.com/assets/cms2/img/pokedex/full/001.png"
      }
      return imgurl
    },
    getNumber: function (pokedexNum) {
      if (this.searchResults.pokedex_number < 10) {
        pokedexNum = "00" + this.searchResults.pokedex_number
      } else if (this.searchResults.pokedex_number < 100) {
        pokedexNum = "0" + this.searchResults.pokedex_number
      } else {
        pokedexNum = "" + this.searchResults.pokedex_number + ""
      }
      return pokedexNum
    },
  },

  methods: {
    onload() {
      let url;
      url = 'http://ec2-34-197-223-156.compute-1.amazonaws.com:8080/api/pokemon/searchAll/'
      axios.get(url)
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
    },

    onSubmit() {
      let url;
      if (isNaN(this.searchQuery)) {
        url = 'http://ec2-34-197-223-156.compute-1.amazonaws.com:8080/api/pokemon/searchName/'
      }
      else {
        url = 'http://ec2-34-197-223-156.compute-1.amazonaws.com:8080/api/pokemon/searchID/'
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
    },
  },
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

</style>
