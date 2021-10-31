<template>
  <div id="app">
    <a href="http://localhost:8080/"><img id="logo" alt="Vue logo" src="./assets/logo.png"></a>
    <h1>Pokedex</h1>
    <template>
      <vue-bootstrap-typehead  :data="addresses" v-model="query" :serializer="s => s.text"
                              placeholder="Search for a Pokemon"    @hit="selectedAddress = $event" :minMatchingChars="1" />
        <p>{{addresses}}</p>
    </template>
    <div class="options">
      <SearchBar v-model="searchQuery" @submit="onSubmit"/>
      <Options v-model="jason" @submit="onClick" />
    </div>

<!--    <PokemonCard v-if="searchResults.length === 0" :content=searchResultsAll />-->
    <Pokemon v-if="searchResults.length !== 0" v-bind:imgsrc="resolveImgSource" :result=searchResults
             :pokedexNumb=getNumber />
    <b-row v-if="Object.keys(jason).length === 0">
      <b-card-group class="allCards">
        <PokemonCard v-for="(value, property, index) in searchResultsAll" v-bind:key="index" :value=value
                     :number=value.pokedex_number />
      </b-card-group>
    </b-row>
  </div>
</template>

<script>
import SearchBar from './components/Searchbar.vue';
import PokemonCard from "@/components/PokemonCard";
import Pokemon from "@/components/Pokemon";
import Options from "@/components/Options";
import VueBootstrapTypehead from 'vue-bootstrap-typeahead'
import _ from 'underscore'
import axios from 'axios';

  const API_URL = 'http://ec2-34-197-223-156.compute-1.amazonaws.com:8080/api/pokemon/autocomplete/'

export default {
  name: 'App',

  components: {
    SearchBar: SearchBar,
    Pokemon: Pokemon,
    PokemonCard: PokemonCard,
    Options: Options,
    VueBootstrapTypehead,
  },

  data() {
    return {
      searchQuery: '',
      searchResults: [],
      searchResultsAll: [],
      jason: {},
      query: '',
      addresses: [],
      selectedAddress: null
    }
  },
  mounted: function() {
    this.$nextTick(function () {
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
    })
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
    onSubmit() {
      let url;
      if (isNaN(this.searchQuery)) {
        url = 'http://ec2-34-197-223-156.compute-1.amazonaws.com:8080/api/pokemon/searchName/'
      } else if (this.searchQuery === '') {
        url = 'http://ec2-34-197-223-156.compute-1.amazonaws.com:8080/api/pokemon/searchAll/'
      } else {
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
    onClick(jason) {
      // Send filter to backend
      axios({
        method: 'post',
        url: 'http://ec2-34-197-223-156.compute-1.amazonaws.com:8080/api/pokemon/filterPokemon',
        data: jason,
        headers: {'Content-Type': 'application/json'},
      })
          .then((response) => {
            if (response.data === null) {
              this.searchResultsAll = [];
            } else {
              this.searchResultsAll = response.data;
              console.log(response.data)
              const object = Object.entries(jason)
              console.log(Object.fromEntries(object))
            }
          })
          .catch((error) => {
            console.log(error);
            this.searchResultsAll = []
          })
    },
    async getAddresses(query) {
      const res = await fetch(API_URL + query)
      const suggestions = await res.json()
      this.addresses = suggestions
      console.log(suggestions)
    },
  },
  watch: {
    query: _.debounce(function (addr) {
      this.getAddresses(addr)}, 500)
  }
}

</script>

<style>
html {
  background-color: #19191B;
}
.allCards {
  display: inline-block !important;
}
.options {
  background-color: #19191B;
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
