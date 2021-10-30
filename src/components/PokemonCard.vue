<template>
  <div class="w-100 p-3 mb-1 text-light card">
    <b-container fluid="lg">
      <b-card-group deck class="deck">
        <b-card id="cards"
                style="max-width: 20rem"
                img-src="https://www.pokewiki.de/images/thumb/9/96/Sugimori_001.png/250px-Sugimori_001.png"
                img-alt="Pokemonname"
                img-top
                header-tag="header"
                footer-tag="footer"
                value>
          <b-card-body class="card-body">
            <b-card-title>{{ name }}</b-card-title>
            <b-card-sub-title class="mb-2">No.000 {{ number }}</b-card-sub-title>
          </b-card-body>
          <b-card-footer>Type: <b-badge class="Grass">{{ type }}</b-badge></b-card-footer>
        </b-card>
      </b-card-group>
    </b-container>
  </div>
</template>

<script>
export default {
  name: "PokemonCard",
  props: {
    content: undefined,
    name: String,
    number: Number,
    type: String,
    searchResults: [],
  },
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

</style>
