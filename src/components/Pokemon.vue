<template>
    <div>
      <h1> {{ result.name }}
        <b-badge variant="dark">№ {{ pokedexNumb }}</b-badge>
      </h1>
      <div class="card-big w-50 p-3 mb-1 mx-auto">
        <b-card-group columns>
          <!-- img -->
          <div class="close">
            <b-button size="sm" class="mb-2  close" onclick="this.searchResults.length = 0" >
              <b-icon icon="x-circle" aria-hidden="true" href="http://localhost:8080/"></b-icon>
            </b-button>
          </div>
          <b-card no-body class="overflow-hidden" style="width:75%">
            <b-row no-gutters id="pokeimg">
              <b-card-img :src="imgsrc" class="img"/>
            </b-row>
          </b-card>
          <!-- stats block -->
          <b-card bg-variant="dark" text-variant="white" id="card1" style="max-width: 100%">
            <b-row no-gutters>
              <b-col><b>Type: </b></b-col>
              <b-col>
                <b-badge :class="result.type_1">{{ result.type_1 }} </b-badge>  <b-badge :class="result.type_2" v-if="result.type_2">{{ result.type_2 }} </b-badge>
              </b-col>
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

            <b-row no-gutters v-if="result.percentage_male">
              <b-col><b>Percentage Male: </b></b-col>
              <b-col>
                <b-progress class="w-75 mb-2" :max="100" show-value variant="secondary" :value="result.percentage_male" />
              </b-col>
            </b-row>

            <b-row no-gutters v-if="result.percentage_male">
              <b-col><b>Percentage Female: </b></b-col>
              <b-col>
                <b-progress class="w-75 mb-2" :max="100" show-value variant="secondary" :value="100-result.percentage_male"/>
              </b-col>
            </b-row>

            <b-row no-gutters v-if="result.percentage_male">
              <b-col><b>Weaknesses: </b></b-col>
              <b-col>
                <div v-for="attr in result" :key="attr.message">
                  {{attr.message}}
                </div>
              </b-col>
            </b-row>

          </b-card>
        </b-card-group>


        <!-- info-card -->
        <b-card-group>
          <b-card bg-variant="dark" text-variant="light">
            <b-row no-gutters>
              <b-col><b>HP: </b></b-col>
              <b-col>
                <b-progress :max="255" show-value variant="success" :value="result.hp"/>
              </b-col>
            </b-row>

            <b-row no-gutters>
            <b-col><b>Attack: </b></b-col>
              <b-col>
                <b-progress :max="190" show-value variant="danger" :value="result.attack"/>
              </b-col>
            </b-row>

            <b-row no-gutters>
              <b-col><b>Defense: </b></b-col>
              <b-col>
                  <b-progress :max="230" show-value variant="primary" :value="result.defense"/>
              </b-col>
            </b-row>

            <b-row no-gutters>
              <b-col><b>Special Attack: </b></b-col>
              <b-col>
                <b-progress :max="173" show-value variant="danger" :value="result.sp_attack"/>
              </b-col>
            </b-row>

            <b-row no-gutters>
              <b-col><b>Special Defense: </b></b-col>
              <b-col>
                <b-progress :max="230" show-value variant="primary" :value="result.sp_defense"/>
              </b-col>
            </b-row>

            <b-row no-gutters>
              <b-col><b>Speed: </b></b-col>
              <b-col>
                <b-progress :max="200" show-value variant="warning" :value="result.speed"/>
              </b-col>
            </b-row>

            <b-row no-gutters>
              <b-col><b>Total Points: </b></b-col>
              <b-col>
                <b-progress :max="720" show-value variant="info" :value="result.total_points"/>
              </b-col>
            </b-row>

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

}
</script>

<style>
#card1 {
  margin-top: 15px !important;
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
  margin-bottom: 0 !important;
}
.close {
  float: left !important;
  color: white !important ;
  opacity: 1 !important;
}
.close:hover, .close:active {
  float: left !important;
  background-color: transparent !important;
  opacity: 1 !important;
}

.col {
  margin-bottom: 0 !important;
}

.card-columns {
  -moz-column-count: 3 !important;
  column-count: 2 !important;
}

.Grass {
  background-color: #078207 !important;
}

.Bug {
  background-color: #005945 !important;
}

.Dragon {
  background-color: #811814 !important;
}

.Fairy {
  background-color: #c65f6d !important;
}

.Fire {
  background-color: #d2581c !important;
}

.Ghost {
  background-color: #2d182b !important;
}

.Ground {
  background-color: #8e7437 !important;
}

.Normal {
  background-color: #958a8a !important;
  color: #090f15 !important;
}

.Psychic {
  background-color: #c92c76 !important;
}

.Steel {
  background-color: #5a5a5a !important;
}

.Dark {
  background-color: #0b1d26 !important;
}

.Electric {
  background-color: #efc213 !important;
  color: #171f2b !important;
}

.Fighting {
  background-color: #C6231A !important;
}

.Flying {
  background-color: #a6cef6 !important;
  color: #171f2b !important;
}

.Ice {
  background-color: #E9F2FF !important;
  color: #171f2b !important;
}

.Poison {
  background-color: #8401B8 !important;
}

.Rock {
  background-color: #5A4D41 !important;
}

.Water {
  background-color: #3677a0 !important;
}

.badge {
  font-weight: 500 !important;
}

</style>
