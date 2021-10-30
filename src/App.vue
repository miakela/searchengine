<template>
  <div id="app">
      <img id="logo" alt="Vue logo" src="./assets/logo.png">
      <h1>Pokedex</h1>
    <div class="options">
    <SearchBar v-model="searchQuery" @submit="onSubmit"/>
      <Options></Options>
    </div>
      <PokemonCard v-if="searchResults.length === 0" :content=searchResultsAll />
      <Pokemon v-if="searchResults.length !== 0" v-bind:imgsrc="resolveImgSource" :result=searchResults :pokedexNumb=getNumber />
      <PokemonCard v-for="(value, propertyname, index) in searchResults" v-bind:key="index" :name=propertyname.name
                   :number=propertyname.pokedex_number :type=propertyname.type_1 />
  </div>
</template>

<script>
import SearchBar from './components/Searchbar.vue';
import PokemonCard from "@/components/PokemonCard";
import Pokemon from "@/components/Pokemon";
import Options from "@/components/Options";

import axios from 'axios';

export default {
  name: 'App',

  components: {
    SearchBar: SearchBar,
    Pokemon: Pokemon,
    PokemonCard: PokemonCard,
    Options: Options,
  },

  data() {
    return {
      searchQuery: '',
      searchResults: [],
      searchResultsAll: []
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
/*    onload() {
      let url;
      url = 'http://ec2-34-197-223-156.compute-1.amazonaws.com:8080/api/pokemon/searchAll/'
      axios.get(url)
          .then((response) => {
            if (response.data === null) {
              this.searchResultsAll = [];
            } else {
              this.searchResultsAll = response.data;
              console.log(this.searchResultsAll)
            }
          })
          .catch((error) => {
            console.log(error);
            this.searchResultsAll = []
          })
    },*/

/*    searchResultsAll() {
        var url = 'http://ec2-34-197-223-156.compute-1.amazonaws.com:8080/api/pokemon/searchAll/'
        axios.get(url)
          .then(response => {
          })
          .catch(error => {
          })
    },*/

    onSubmit() {
      let url;
      if (isNaN(this.searchQuery)) {
        url = 'http://ec2-34-197-223-156.compute-1.amazonaws.com:8080/api/pokemon/searchName/'
      }
      else if (this.searchQuery === ''){
        url = 'http://ec2-34-197-223-156.compute-1.amazonaws.com:8080/api/pokemon/searchAll/'
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
              console.log(response.data)
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

.options {
  background-color: #19191B;
}

.bottom {
}

#app {
  font-family: "Open Sans", sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #eeeeee;
  padding-top: 60px;
  background-color: #19191B;
}

#logo {
  width: 40%;
}
body::-webkit-scrollbar {
  display: block;
  background-color: #19191B;
  width: 0.5rem;

}
body::-webkit-scrollbar-thumb {
  background: #29292F;
  border-radius: 10px;
}

</style>
