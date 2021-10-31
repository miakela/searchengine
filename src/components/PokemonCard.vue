<template>
        <b-card id="cards"
                style="max-width: 20rem; display:inline-block"
                img-alt="PokemonImage"
                img-top
                :img-src=resolveImgSource(number)
                header-tag="header"
                footer-tag="footer"
                value>
<!--          <b-card-img v-on:change="resolveImgSource(number)" v-bind:img-src=resolveImgSource(number)></b-card-img>-->
          <b-card-body class="card-body">
            <b-card-title class="title">{{ value.name }}</b-card-title>
            <b-card-sub-title v-on:change="getNumber(number)" class="mb-2">№ {{getNumber(number)}}</b-card-sub-title>
          </b-card-body>
          <b-card-footer>Type: <b-badge :class="value.type_1" >{{value.type_1}}</b-badge>  <b-badge v-if="value.type_2" :class="value.type_2" >{{value.type_2}}</b-badge></b-card-footer>
        </b-card>
</template>

<script>
export default {
  name: "PokemonCard",
  props: {
    value: Object,
    number: Number,
    pokedexNumb: String,
    searchResultsAll: [],
  },


 methods: {
 getNumber: function(pokedexNum) {
    if (this.number < 10) {
      pokedexNum = "00" + this.number
    } else if (this.number < 100) {
      pokedexNum = "0" + this.number
    } else {
      pokedexNum = "" + this.number + ""
    }
    return pokedexNum
  },
   resolveImgSource: function (pokedexNum) {
     let imgurl;
     /*this.searchResults.pokedex_number*/
     if ((pokedexNum) < 10) {
       imgurl = "https://assets.pokemon.com/assets/cms2/img/pokedex/full/00" + pokedexNum + ".png"
     } else if ((pokedexNum) < 100) {
       imgurl = "https://assets.pokemon.com/assets/cms2/img/pokedex/full/0" + pokedexNum + ".png"
     } else if ((pokedexNum) < 1000) {
       imgurl = "https://assets.pokemon.com/assets/cms2/img/pokedex/full/" + pokedexNum + ".png"
     } else {
       imgurl = "https://assets.pokemon.com/assets/cms2/img/pokedex/full/001.png"
     }
     return imgurl
   },
 }
}
</script>

<style>
#cards {
  background-color: #29292F !important;
  border-radius: 8px;
  margin: 20px;
}

#cards img {
  width: 50%;
  padding-top: 20px;
  margin-left: auto;
  margin-right: auto;
}

.card-body {
  text-align: left;
  /*padding-bottom: 0 !important;*/
}

.card {
  border: 0 !important;
  background-color: #19191B !important;
  margin-left: auto;
  margin-right: auto;
  margin-bottom: 30px !important;
}

.ability {
  padding: 0.2rem 0.4rem !important;
  font-size: 75% !important;
  color: #fff !important;
  background-color: #212529 !important;
  border-radius: 0.2rem !important;
  margin-left: 15px;
  margin-bottom: 15px;
}
.title{
  margin-bottom: 1px!important;
}

</style>
