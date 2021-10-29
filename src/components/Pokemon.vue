<template>
  <div>
    <h1> {{ result.name }}
      <b-badge variant="dark">№{{ pokedexNumb }}</b-badge>
    </h1>
    <div class="card-big">
      <b-card-group columns>
        <!-- img -->
        <b-card no-body class="overflow-hidden">
          <b-row no-gutters>
            <b-card-img :src="imgsrc" class="img"/>
          </b-row>
        </b-card>
        <!-- stats block -->
        <b-card bg-variant="dark" text-variant="white" id="card1" style="max-width: 100%">
          <b-row no-gutters>
            <b-col><b>Type: </b></b-col>
            <b-col><b-badge>{{result.type_2}}</b-badge></b-col>
          </b-row>

          <b-row no-gutters>
            <b-col><b>Size:</b></b-col>
            <b-col> {{ result.height_m }} m</b-col>
          </b-row>

          <b-row no-gutters>
            <b-col><b>Weight:</b></b-col>
            <b-col>{{ result.weight_kg }} kg</b-col>
          </b-row>

          <b-row no-gutters>
            <b-col><b>Ability:</b></b-col>
            <b-col>{{ result.ability_1 }}</b-col>
          </b-row>

          <b-row no-gutters>
            <b-col><b>Percentage Male: </b></b-col>
            <b-col>
              <b-progress class="w-75 mb-2" :max="max" show-value>
                <b-progress-bar :value="20"></b-progress-bar>
              </b-progress>
            </b-col>
          </b-row>
          <b-row no-gutters>
            <b-col><b>Percentage Female: </b></b-col>
            <b-col>
              <b-progress class="w-75 mb-2" :max="max" show-value>
                <b-progress-bar :value="40" ></b-progress-bar>
              </b-progress>
            </b-col>
          </b-row>

        </b-card>
      </b-card-group>

      <b-card-group columns>
        <!-- info-card -->
        <b-card bg-variant="light" text-variant="dark">
          <blockquote class="card-blockquote">
            <p>Lorem ipsum dolor sit amet, consectetur adipiscing elit. Integer posuere erat a ante.</p>
            <footer>
              <small>Someone famous in <cite title="Source Title">Source Title</cite></small>
            </footer>
          </blockquote>
        </b-card>

        <b-card>
          <b-card-title>Title</b-card-title>
          <b-card-text>
            This card has supporting text below as a natural lead-in to additional content.
          </b-card-text>
          <b-card-text class="small text-muted">Last updated 3 mins ago</b-card-text>
        </b-card>

      </b-card-group>
    </div>
  </div>
</template>

<script>
export default {
  name: "Pokemon",
  props: {
    imgsrc: String,
    result: [],
    pokedexNumb: String,
    value: Number,
  },

  data() {
    return {
      max: 100,
    }
  }
}
</script>

<style>
#card1 {
  margin-top: 20px !important;
}

.img {
  background-color: #212529 !important;
}

.col {
  margin-top: 9px;
}

.card-big {
  background-color: #212529;
  padding: 20px;
  border-radius: 8px;
  margin: 24px 0 24px 0;
}

h4 {
  margin-bottom: 0rem !important;
}
.col {
  margin-bottom: 0 !important;
}

.card-columns {
  -moz-column-count: 3 !important;
  column-count: 2 !important;
}
.grass {
  background-color: #009400!important;
}
.badge {
  font-weight: 500!important;
}
</style>