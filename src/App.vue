<template>
  <div id="app">
    <img id="logo" alt="Vue logo" src="./assets/logo.png">
    <SearchBar msg="Pokedex"/>
    <PokemonCard id="card"/>
  </div>
</template>

<script>
import SearchBar from './components/Searchbar.vue'
import PokemonCard from "@/components/PokemonCard";

export default {
  name: 'App',
  components: {
    SearchBar: SearchBar,
    PokemonCard: PokemonCard
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
