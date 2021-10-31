<template>
  <div>
    <template>
      <div class="accordion w-50 p-3 mb-1 mx-auto" role="tablist">
        <b-card no-body class="mb-1">
          <b-card-header header-tag="header" class="p-1" role="tab">
            <b-button block v-b-toggle.accordion-1 style="background-color: #29292F">Advanced Search
              <b-icon icon="chevron-bar-down"></b-icon>
            </b-button>
          </b-card-header>

          <b-collapse id="accordion-1" accordion="my-accordion" role="tabpanel" title="Type">
            <b-card-group column>
              <!--                whole dropdown   -->
              <b-card-group>
                <!--              left column Type & Weakness-->
                <div class="marginType">
                  <b-card-title align="left" class="title">Type & Weakness</b-card-title>
                  <b-card-group>
                    <b-list-group>
                      <b-list-group-item align="left"><span class="round Bug">Bug</span>
                        <b-form-checkbox v-model="selectedType" value="Bug" button button-variant="outline-light">
                          T
                        </b-form-checkbox>
                        <b-form-checkbox v-model="selectedWeakness" value="against_bug" button button-variant="outline-light">
                          W
                        </b-form-checkbox>
                      </b-list-group-item>
                      <b-list-group-item align="left"><span class="round Dragon">Dragon</span>
                        <b-form-checkbox v-model="selectedType" value="Dragon" button button-variant="outline-light">
                          T
                        </b-form-checkbox>
                        <b-form-checkbox v-model="selectedWeakness" value="against_dragon" button button-variant="outline-light">
                          W
                        </b-form-checkbox>
                      </b-list-group-item>
                      <b-list-group-item align="left"><span class="round Fairy">Fairy</span>
                        <b-form-checkbox v-model="selectedType" value="Fairy" button button-variant="outline-light">
                          T
                        </b-form-checkbox>
                        <b-form-checkbox v-model="selectedWeakness" value="against_fairy" button button-variant="outline-light">
                          W
                        </b-form-checkbox>
                      </b-list-group-item>
                      <b-list-group-item align="left"><span class="round Fire">Fire</span>
                        <b-form-checkbox v-model="selectedType" value="Fire" button button-variant="outline-light">
                          T
                        </b-form-checkbox>
                        <b-form-checkbox v-model="selectedWeakness" value="against_fire" button button-variant="outline-light">
                          W
                        </b-form-checkbox>
                      </b-list-group-item>
                      <b-list-group-item align="left"><span class="round Ghost">Ghost</span>
                        <b-form-checkbox v-model="selectedType" value="Ghost" button button-variant="outline-light">
                          T
                        </b-form-checkbox>
                        <b-form-checkbox v-model="selectedWeakness" value="against_ghost" button button-variant="outline-light">
                          W
                        </b-form-checkbox>
                      </b-list-group-item>
                      <b-list-group-item align="left"><span class="round Ground">Ground</span>
                        <b-form-checkbox v-model="selectedType" value="Ground" button button-variant="outline-light">
                          T
                        </b-form-checkbox>
                        <b-form-checkbox v-model="selectedWeakness" value="against_ground" button button-variant="outline-light">
                          W
                        </b-form-checkbox>
                      </b-list-group-item>
                      <b-list-group-item align="left"><span class="round Normal">Normal</span>
                        <b-form-checkbox v-model="selectedType" value="Normal" button button-variant="outline-light">
                          T
                        </b-form-checkbox>
                        <b-form-checkbox v-model="selectedWeakness" value="against_normal" button button-variant="outline-light">
                          W
                        </b-form-checkbox>
                      </b-list-group-item>
                      <b-list-group-item align="left"><span class="round Psychic">Psychic</span>
                        <b-form-checkbox v-model="selectedType" value="Psychic" button button-variant="outline-light">
                          T
                        </b-form-checkbox>
                        <b-form-checkbox v-model="selectedWeakness" value="against_psychic" button button-variant="outline-light">
                          W
                        </b-form-checkbox>
                      </b-list-group-item>
                      <b-list-group-item align="left"><span class="round Steel">Steel</span>
                        <b-form-checkbox v-model="selectedType" value="Steel" button button-variant="outline-light">
                          T
                        </b-form-checkbox>
                        <b-form-checkbox v-model="selectedWeakness" value="against_steel" button button-variant="outline-light">
                          W
                        </b-form-checkbox>
                      </b-list-group-item>

                    </b-list-group>
                    <b-list-group>
                      <b-list-group-item align="left"><span class="round Dark">Dark</span>
                        <b-form-checkbox v-model="selectedType" value="Dark" button button-variant="outline-light">
                          T
                        </b-form-checkbox>
                        <b-form-checkbox v-model="selectedWeakness" value="against_dark" button button-variant="outline-light">
                          W
                        </b-form-checkbox>
                      </b-list-group-item>
                      <b-list-group-item align="left"><span class="round Electric">Electric</span>
                        <b-form-checkbox v-model="selectedType" value="Electric" button button-variant="outline-light">
                          T
                        </b-form-checkbox>
                        <b-form-checkbox v-model="selectedWeakness" value="against_electric" button button-variant="outline-light">
                          W
                        </b-form-checkbox>
                      </b-list-group-item>
                      <b-list-group-item align="left"><span class="round Fighting">Fighting</span>
                        <b-form-checkbox v-model="selectedType" value="Fighting" button button-variant="outline-light">
                          T
                        </b-form-checkbox>
                        <b-form-checkbox v-model="selectedWeakness" value="against_fighting" button button-variant="outline-light">
                          W
                        </b-form-checkbox>
                      </b-list-group-item>
                      <b-list-group-item align="left"><span class="round Flying">Flying</span>
                        <b-form-checkbox v-model="selectedType" value="Flying" button button-variant="outline-light">
                          T
                        </b-form-checkbox>
                        <b-form-checkbox v-model="selectedWeakness" value="against_flying" button button-variant="outline-light">
                          W
                        </b-form-checkbox>
                      </b-list-group-item>
                      <b-list-group-item align="left"><span class="round Grass">Grass</span>
                        <b-form-checkbox v-model="selectedType" value="Grass" button button-variant="outline-light">
                          T
                        </b-form-checkbox>
                        <b-form-checkbox v-model="selectedWeakness" value="against_grass" button button-variant="outline-light">
                          W
                        </b-form-checkbox>
                      </b-list-group-item>
                      <b-list-group-item align="left"><span class="round Ice">Ice</span>
                        <b-form-checkbox v-model="selectedType" value="Ice" button button-variant="outline-light">
                          T
                        </b-form-checkbox>
                        <b-form-checkbox v-model="selectedWeakness" value="against_ice" button button-variant="outline-light">
                          W
                        </b-form-checkbox>
                      </b-list-group-item>
                      <b-list-group-item align="left"><span class="round Poison">Poison</span>
                        <b-form-checkbox v-model="selectedType" value="Poison" button button-variant="outline-light">
                          T
                        </b-form-checkbox>
                        <b-form-checkbox v-model="selectedWeakness" value="against_poison" button button-variant="outline-light">
                          W
                        </b-form-checkbox>
                      </b-list-group-item>
                      <b-list-group-item align="left"><span class="round Rock">Rock</span>
                        <b-form-checkbox v-model="selectedType" value="Rock" button button-variant="outline-light">
                          T
                        </b-form-checkbox>
                        <b-form-checkbox v-model="selectedWeakness" value="against_rock" button button-variant="outline-light">
                          W
                        </b-form-checkbox>
                      </b-list-group-item>
                      <b-list-group-item align="left"><span class="round Water">Water</span>
                        <b-form-checkbox v-model="selectedType" value="Water" button button-variant="outline-light">
                          T
                        </b-form-checkbox>
                        <b-form-checkbox v-model="selectedWeakness" value="against_water" button button-variant="outline-light">
                          W
                        </b-form-checkbox>
                      </b-list-group-item>

                    </b-list-group>
                  </b-card-group>
                </div>
              </b-card-group>

              <!--              right column Ability-->
              <b-card-group class="marginleft">
                <div>
                  <b-card-group>
                    <b-card-title align="left" class="title">Ability</b-card-title>
                    <b-form-select v-model="selectedAbility" :options="Abilities"
                                   style="background-color: #29292F; color:white "></b-form-select>
                  </b-card-group>

                  <b-form-group>
                    <b-card-title align="left" class="title">Height</b-card-title>
                    <div>
                      <b-form-checkbox-group
                          v-model="selectedHeight"
                          buttons
                          button-variant="dark"
                          size="lg"
                          name="buttons-2"
                      ><b-form-checkbox v-model="selectedHeight" value=1 unchecked-value=null >small</b-form-checkbox>
                        <b-form-checkbox v-model="selectedHeight" value=2 unchecked-value=null >medium</b-form-checkbox>
                        <b-form-checkbox v-model="selectedHeight" value=3 unchecked-value=null >large</b-form-checkbox>
                      </b-form-checkbox-group>
                    </div>
                  </b-form-group>

                  <b-form-group>
                    <b-card-title align="left" class="title">Weight</b-card-title>
                    <div>
                      <b-form-checkbox-group
                          v-model="selectedWeight"
                          buttons
                          button-variant="dark"
                          size="lg"
                          name="buttons-2"
                      ><b-form-checkbox v-model="selectedWeight" value=1 unchecked-value=null >light</b-form-checkbox>
                        <b-form-checkbox v-model="selectedWeight" value=2 unchecked-value=null >medium</b-form-checkbox>
                        <b-form-checkbox v-model="selectedWeight" value=3 unchecked-value=null >heavy</b-form-checkbox>
                      </b-form-checkbox-group>
                    </div>
                  </b-form-group>

                  <b-card-group>
                    <b-card-title align="left" class="title">Sorty By</b-card-title>
                    <b-form-select v-model="sort" :options="sortBy"
                                   style="background-color: #29292F; color:white "></b-form-select>
                    <div class="idek">
                    <div class="form-check form-check-inline">
                      <input v-model="ordered" class="form-check-input" type="radio" name="inlineRadioOptions" id="inlineRadio1" value="ASC">
                      <label class="form-check-label" for="inlineRadio1">Ascending ↑</label>
                    </div>
                    <div class="form-check form-check-inline">
                      <input v-model="ordered" class="form-check-input" type="radio" name="inlineRadioOptions" id="inlineRadio2" value="DESC">
                      <label class="form-check-label" for="inlineRadio2">Descending ↓</label>
                    </div>
                    </div>
                  </b-card-group>

                  <b-card-group>
                    <b-card-body>
                  <div class="form-check form-check-inline">
                    <b-checkbox v-model="legendary" class="form-check-input" name="legendaryOption" value=1 unchecked-value=0 />
                    <label class="form-check-label">Legendary Pokemon</label>
                  </div>
                    </b-card-body>
                  </b-card-group>

                  <b-form-group class="iconSearch">
                      <b-button v-on:click="reset">Reset
                      </b-button>
                      <b-button v-on:click="onClick">Search
                        <b-icon icon="search" size="sm" ></b-icon>
                      </b-button>
                  </b-form-group>

                </div>
              </b-card-group>
            </b-card-group>
          </b-collapse>
        </b-card>
      </div>
    </template>
  </div>
</template>


<script>
export default {
  data() {
    return {
      jason: {},
      legendary: null,
      sort: null,
      ordered: null,
      selectedType: [],
      selectedWeakness: [],
      selectedAbility: null,
      selectedHeight: null,
      selectedWeight: null,
      sortBy: [
        {value: "ability", text: "Ability"},
        {value: "height_m", text: "Height"},
        {value: "pokedex_number", text: "Number"},
        {value: "type_1", text: 'Type'},
        {value: "weakness", text: "Weaknesses"},
        {value: "weight_kg", text: "Weight"},
      ],
      height: [
        {item: 1, name: 'small'},
        {item: 2, name: 'medium'},
        {item: 3, name: 'large',},
      ],
      weight: [
        {item: 1, name: 'light'},
        {item: 2, name: 'medium'},
        {item: 3, name: 'heavy'},
      ],
        Abilities: [
      "Adaptability",
      "Aerilate",
      "Aftermath",
      "Air Lock",
      "Anticipation",
      "As One",
      "Aura Break",
      "Bad Dreams",
      "Ball Fetch",
      "Battery",
      "Battle Armor",
      "Battle Bond",
      "Beast Boost",
      "Berserk",
      "Big Pecks",
      "Blaze",
      "Bulletproof",
      "Cheek Pouch",
      "Chilling Neigh",
      "Chlorophyll",
      "Clear Body",
      "Color Change",
      "Comatose",
      "Competitive",
      "Compound Eyes",
      "Contrary",
      "Corrosion",
      "Cotton Down",
      "Curious Medicine",
      "Cursed Body",
      "Cute Charm",
      "Damp",
      "Dancer",
      "Dark Aura",
      "Dauntless Shield",
      "Dazzling",
      "Defeatist",
      "Defiant",
      "Delta Stream",
      "Desolate Land",
      "Disguise",
      "Download",
      "Dragon‘s Maw",
      "Drizzle",
      "Drought",
      "Dry Skin",
      "Early Bird",
      "Effect Spore",
      "Electric Surge",
      "Emergency Exit",
      "Fairy Aura",
      "Filter",
      "Flame Body",
      "Flash Fire",
      "Flower Gift",
      "Flower Veil",
      "Fluffy",
      "Forecast",
      "Forewarn",
      "Frisk",
      "Full Metal Body",
      "Fur Coat",
      "Gluttony",
      "Gorilla Tactics",
      "Grassy Surge",
      "Grim Neigh",
      "Gulp Missile",
      "Guts",
      "Healer",
      "Honey Gather",
      "Huge Power",
      "Hunger Switch",
      "Hustle",
      "Hydration",
      "Hyper Cutter",
      "Ice Body",
      "Ice Face",
      "Illuminate",
      "Illusion",
      "Immunity",
      "Innards Out",
      "Inner Focus",
      "Insomnia",
      "Intimidate",
      "Intrepid Sword",
      "Iron Barbs",
      "Iron Fist",
      "Justified",
      "Keen Eye",
      "Leaf Guard",
      "Levitate",
      "Light Metal",
      "Lightning Rod",
      "Limber",
      "Liquid Ooze",
      "Magic Bounce",
      "Magician",
      "Magma Armor",
      "Magnet Pull",
      "Marvel Scale",
      "Mega Launcher",
      "Merciless",
      "Mimicry",
      "Minus",
      "Misty Surge",
      "Mold Breaker",
      "Motor Drive",
      "Multitype",
      "Mummy",
      "Natural Cure",
      "Neuroforce",
      "No Guard",
      "Oblivious",
      "Overcoat",
      "Overgrow",
      "Own Tempo",
      "Parental Bond",
      "Pickup",
      "Pixilate",
      "Plus",
      "Poison Point",
      "Poison Touch",
      "Power Construct",
      "Power Spot",
      "Prankster",
      "Pressure",
      "Primordial Sea",
      "Prism Armor",
      "Psychic Surge",
      "Punk Rock",
      "Pure Power",
      "Quick Draw",
      "RKS System",
      "Rattled",
      "Receiver",
      "Reckless",
      "Refrigerate",
      "Regenerator",
      "Ripen",
      "Rivalry",
      "Rock Head",
      "Rough Skin",
      "Run Away",
      "Sand Force",
      "Sand Rush",
      "Sand Spit",
      "Sand Stream",
      "Sand Veil",
      "Sap Sipper",
      "Schooling",
      "Scrappy",
      "Serene Grace",
      "Shadow Shield",
      "Shadow Tag",
      "Shed Skin",
      "Sheer Force",
      "Shell Armor",
      "Shield Dust",
      "Shields Down",
      "Simple",
      "Skill Link",
      "Slow Start",
      "Sniper",
      "Snow Cloak",
      "Snow Warning",
      "Solar Power",
      "Solid Rock",
      "Soul-Heart",
      "Soundproof",
      "Speed Boost",
      "Stance Change",
      "Static",
      "Steadfast",
      "Steam Engine",
      "Steelworker",
      "Stench",
      "Sticky Hold",
      "Strong Jaw",
      "Sturdy",
      "Suction Cups",
      "Surge Surfer",
      "Swarm",
      "Sweet Veil",
      "Swift Swim",
      "Synchronize",
      "Tangled Feet",
      "Technician",
      "Telepathy",
      "Teravolt",
      "Thick Fat",
      "Torrent",
      "Tough Claws",
      "Trace",
      "Transistor",
      "Truant",
      "Turboblaze",
      "Unaware",
      "Unnerve",
      "Unseen Fist",
      "Victory Star",
      "Vital Spirit",
      "Volt Absorb",
      "Wandering Spirit",
      "Water Absorb",
      "Water Bubble",
      "Water Compaction",
      "Water Veil",
      "Weak Armor",
      "White Smoke",
      "Wimp Out",
      "Wonder Guard",
      "Wonder Skin"
    ],
  }
  },

  name: "Options",
  methods: {
    onClick(event) {
      event.preventDefault();
      if (this.selectedType.length !== 0) {
        this.jason['type_1'] = this.selectedType;
      }
      if (this.selectedAbility != null) {
        this.jason['ability'] = this.selectedAbility;
      }
      if (this.selectedWeakness.length  !== 0) {
        this.jason['weakness'] = this.selectedWeakness;
      }
      if (this.selectedWeight!= null) {
        this.jason['weight'] = this.selectedWeight;
      }
      if (this.selectedHeight!= null) {
        this.jason['height'] = this.selectedHeight;
      }
      if (this.legendary != null ){
        this.jason['legendary'] = this.legendary;
      }
      if (this.sort != null) {
        let sortArr = [null, null];
        sortArr[0] = this.sort;
        sortArr[1] = this.ordered;
        this.jason['sort'] = sortArr;
      }
      this.$emit('submit', this.jason);
    },
    reset(){
      this.sort = null;
      this.ordered = null;
      this.selectedType = [];
      this.selectedWeakness = [];
      this.selectedAbility = null;
      this.selectedHeight = null;
      this.selectedWeight = null;
      this.legendary = null;
    }
  }
}

</script>

<style>
.idek {
  font-size: 12px;
  padding-top: 6px;
  padding-left: 6px;
}

.navbar {
  background-color: #29292F !important;
  border-radius: 8px;
}

.filter {
  font-size: 18px;
  color: rgba(255, 255, 255, 0.5);
  font-weight: lighter;
}

.oL {
  background-color: white !important;
  color: #19191B !important;
  width: 22px;
  height: 22px;
  text-align: center !important;
  border-radius: 50% !important;
  padding: 6px !important;
}

.list-group-item {
  background-color: #343A40 !important;
  border-color: #343A40 !important;
}

.round {
  border-radius: 5px;
  width: 110px;
  padding: 0 20px 0 20px;

}

.card-header.p-1 {
  background-color: #29292F;
}

.btn.btn-secondary.btn-block.not-collapsed {
  background-color: #29292F;
  border: 0 #29292F !important;
}

.btn.btn-secondary.btn-block.collapsed {
  background-color: #29292F;
  border: 0 #29292F !important;
}
.custom-select {
  margin-right: 20px !important;
}

.collapse.show {
  background-color: #29292F;
}

.backgroundcolor {
  background-color: #29292F !important;
}

.list-group-item {
  background-color: #29292F !important;
  border: 0px !important;
}

.btn.btn-outline-light.active, .btn.btn-outline-light {
  line-height: 100%;
  vertical-align: middle;
  width: 26px;
  height: 26px;
  border-radius: 50% !important;
  padding: 4px 0 5px 0 !important;
  margin-left: 4px;
}

.title {
  margin: 28px 8px 8px 0 !important;
}

.marginType {
  margin-left: 30px;
  margin-bottom: 40px;
}

.marginleft {
  margin-left: 30px;
}

.dropdown-menu {
  max-height: 280px;
  overflow-y: auto;
}

.dropdown-toggle::after {
  margin-left: 200px !important;
}


.searchButton {
  alignment: right !important;
  margin-top: 10px !important;
  margin-left: 80px !important;
}

.iconSearch {
  margin-top: 40px ;
  margin-left: 150px;
}
.btn.btn-secondary {
  margin-left: 3px!important;
}

</style>