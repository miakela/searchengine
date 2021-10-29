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
                <b-progress class="w-75 mb-2" :max="100" show-value>
                  <b-progress-bar variant="secondary" :value="result.percentage_male"></b-progress-bar>
                </b-progress>
              </b-col>
            </b-row>
            <b-row no-gutters v-if="result.percentage_male">
              <b-col><b>Percentage Female: </b></b-col>
              <b-col>
                <b-progress class="w-75 mb-2" :max="100" show-value>
                  <b-progress-bar variant="secondary" :value="100-result.percentage_male"></b-progress-bar>
                </b-progress>
              </b-col>
            </b-row>

          </b-card>
        </b-card-group>

        <b-card-group>
          <!-- info-card -->
          <b-card bg-variant="light" text-variant="dark">
            <b-row no-gutters>
              <b-col><b>HP: </b></b-col>
              <b-col>
                <b-progress  :max="255" show-value>
                  <b-progress-bar variant="secondary" :value="result.hp"></b-progress-bar>
                </b-progress>
              </b-col>
            </b-row>

            <b-row no-gutters>
            <b-col><b>Attack: </b></b-col>
              <b-col>
                <b-progress :max="190" show-value>
                  <b-progress-bar variant="secondary" :value="result.attack"></b-progress-bar>
                </b-progress>
              </b-col>
            </b-row>

            <b-row no-gutters>
              <b-col><b>Defense: </b></b-col>
              <b-col>
                <b-progress :max="230" show-value>
                  <b-progress-bar variant="secondary" :value="result.defense"></b-progress-bar>
                </b-progress>
              </b-col>
            </b-row>

            <b-row no-gutters>
              <b-col><b>Special Attack: </b></b-col>
              <b-col>
                <b-progress :max="173" show-value>
                  <b-progress-bar variant="secondary" :value="result.sp_attack"></b-progress-bar>
                </b-progress>
              </b-col>
            </b-row>

            <b-row no-gutters>
              <b-col><b>Special Defense: </b></b-col>
              <b-col>
                <b-progress :max="230" show-value>
                  <b-progress-bar variant="secondary" :value="result.sp_defense"></b-progress-bar>
                </b-progress>
              </b-col>
            </b-row>

            <b-row no-gutters>
              <b-col><b>Speed: </b></b-col>
              <b-col>
                <b-progress :max="200" show-value>
                  <b-progress-bar variant="secondary" :value="result.speed"></b-progress-bar>
                </b-progress>
              </b-col>
            </b-row>

            <b-row no-gutters>
              <b-col><b>Total Points: </b></b-col>
              <b-col>
                <b-progress :max="720" show-value>
                  <b-progress-bar variant="secondary" :value="result.total_points"></b-progress-bar>
                </b-progress>
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

.Grass {
  background-color: #009400 !important;
}

.Bug {
  background-color: #005945 !important;
}

.Dragon {
  background-color: #811814 !important;
}

.Fairy {
  background-color: #EAC1C7 !important;
}

.Fire {
  background-color: #ED5812 !important;
}

.Ghost {
  background-color: #362C35 !important;
}

.Ground {
  background-color: #BF9E5B !important;
}

.Normal {
  background-color: #CDC7B7 !important;
}

.Psychic {
  background-color: #F7138F !important;
}

.Steel {
  background-color: #757575 !important;
}

.Dark {
  background-color: #18242E !important;
}

.Electric {
  background-color: #F7EC00 !important;
}

.Fighting {
  background-color: #C6231A !important;
}

.Flying {
  background-color: #BFDCF7 !important;
}

.Ice {
  background-color: #E9F2FF !important;
}

.Poison {
  background-color: #8401B8 !important;
}

.rock {
  background-color: #5A4D41 !important;
}

.water {
  background-color: #4CA6CD !important;
}


.badge {
  font-weight: 500 !important;
}
</style>