<template>
  <div>

    <div>SelectedTBug: {{ selectedTBug }}</div>
    <div>SelectedWBug: {{ selectedWBug }}</div>
    <div>Selected: {{ selected }}</div>
    <div>selectedAbility: {{ selectedAbility }}</div>
    <div>height: {{ height }}</div>


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
                        <b-form-checkbox v-model="selectedTBug" button button-variant="outline-light">
                          T
                        </b-form-checkbox>
                        <b-form-checkbox v-model="selectedWBug" button button-variant="outline-light">
                          W
                        </b-form-checkbox>
                      </b-list-group-item>
                      <b-list-group-item align="left"><span class="round Dragon">Dragon</span>
                        <b-form-checkbox v-model="selectedTDragon" button button-variant="outline-light">
                          T
                        </b-form-checkbox>
                        <b-form-checkbox v-model="selectedWDragon" button button-variant="outline-light">
                          W
                        </b-form-checkbox>
                      </b-list-group-item>
                      <b-list-group-item align="left"><span class="round Fairy">Fairy</span>
                        <b-form-checkbox v-model="selectedTFairy" button button-variant="outline-light">
                          T
                        </b-form-checkbox>
                        <b-form-checkbox v-model="selectedWFairy" button button-variant="outline-light">
                          W
                        </b-form-checkbox>
                      </b-list-group-item>
                      <b-list-group-item align="left"><span class="round Fire">Fire</span>
                        <b-form-checkbox v-model="selectedTFire" button button-variant="outline-light">
                          T
                        </b-form-checkbox>
                        <b-form-checkbox v-model="selectedWFire" button button-variant="outline-light">
                          W
                        </b-form-checkbox>
                      </b-list-group-item>
                      <b-list-group-item align="left"><span class="round Ghost">Ghost</span>
                        <b-form-checkbox v-model="selectedTGhost" button button-variant="outline-light">
                          T
                        </b-form-checkbox>
                        <b-form-checkbox v-model="selectedWGhost" button button-variant="outline-light">
                          W
                        </b-form-checkbox>
                      </b-list-group-item>
                      <b-list-group-item align="left"><span class="round Ground">Ground</span>
                        <b-form-checkbox v-model="selectedTGround" button button-variant="outline-light">
                          T
                        </b-form-checkbox>
                        <b-form-checkbox v-model="selectedWGround" button button-variant="outline-light">
                          W
                        </b-form-checkbox>
                      </b-list-group-item>
                      <b-list-group-item align="left"><span class="round Normal">Normal</span>
                        <b-form-checkbox v-model="selectedTNormal" button button-variant="outline-light">
                          T
                        </b-form-checkbox>
                        <b-form-checkbox v-model="selectedWNormal" button button-variant="outline-light">
                          W
                        </b-form-checkbox>
                      </b-list-group-item>
                      <b-list-group-item align="left"><span class="round Psychic">Psychic</span>
                        <b-form-checkbox v-model="selectedTPsychic" button button-variant="outline-light">
                          T
                        </b-form-checkbox>
                        <b-form-checkbox v-model="selectedWPsychic" button button-variant="outline-light">
                          W
                        </b-form-checkbox>
                      </b-list-group-item>
                      <b-list-group-item align="left"><span class="round Steel">Steel</span>
                        <b-form-checkbox v-model="selectedTSteel" button button-variant="outline-light">
                          T
                        </b-form-checkbox>
                        <b-form-checkbox v-model="selectedWSteel" button button-variant="outline-light">
                          W
                        </b-form-checkbox>
                      </b-list-group-item>

                    </b-list-group>
                    <b-list-group>
                      <b-list-group-item align="left"><span class="round Dark">Dark</span>
                        <b-form-checkbox v-model="selectedTDark" button button-variant="outline-light">
                          T
                        </b-form-checkbox>
                        <b-form-checkbox v-model="selectedWDark" button button-variant="outline-light">
                          W
                        </b-form-checkbox>
                      </b-list-group-item>
                      <b-list-group-item align="left"><span class="round Electric">Electric</span>
                        <b-form-checkbox v-model="selectedTElectric" button button-variant="outline-light">
                          T
                        </b-form-checkbox>
                        <b-form-checkbox v-model="selectedWElectric" button button-variant="outline-light">
                          W
                        </b-form-checkbox>
                      </b-list-group-item>
                      <b-list-group-item align="left"><span class="round Fighting">Fighting</span>
                        <b-form-checkbox v-model="selectedTFighting" button button-variant="outline-light">
                          T
                        </b-form-checkbox>
                        <b-form-checkbox v-model="selectedWFighting" button button-variant="outline-light">
                          W
                        </b-form-checkbox>
                      </b-list-group-item>
                      <b-list-group-item align="left"><span class="round Flying">Flying</span>
                        <b-form-checkbox v-model="selectedTFlying" button button-variant="outline-light">
                          T
                        </b-form-checkbox>
                        <b-form-checkbox v-model="selectedW" button button-variant="outline-light">
                          W
                        </b-form-checkbox>
                      </b-list-group-item>
                      <b-list-group-item align="left"><span class="round Grass">Grass</span>
                        <b-form-checkbox v-model="selectedTGrass" button button-variant="outline-light">
                          T
                        </b-form-checkbox>
                        <b-form-checkbox v-model="selectedWGrass" button button-variant="outline-light">
                          W
                        </b-form-checkbox>
                      </b-list-group-item>
                      <b-list-group-item align="left"><span class="round Ice">Ice</span>
                        <b-form-checkbox v-model="selectedTIce" button button-variant="outline-light">
                          T
                        </b-form-checkbox>
                        <b-form-checkbox v-model="selectedWIce" button button-variant="outline-light">
                          W
                        </b-form-checkbox>
                      </b-list-group-item>
                      <b-list-group-item align="left"><span class="round Poison">Poison</span>
                        <b-form-checkbox v-model="selectedTPoison" button button-variant="outline-light">
                          T
                        </b-form-checkbox>
                        <b-form-checkbox v-model="selectedWPoison" button button-variant="outline-light">
                          W
                        </b-form-checkbox>
                      </b-list-group-item>
                      <b-list-group-item align="left"><span class="round Rock">Rock</span>
                        <b-form-checkbox v-model="selectedTRock" button button-variant="outline-light">
                          T
                        </b-form-checkbox>
                        <b-form-checkbox v-model="selectedWRock" button button-variant="outline-light">
                          W
                        </b-form-checkbox>
                      </b-list-group-item>
                      <b-list-group-item align="left"><span class="round Water">Water</span>
                        <b-form-checkbox v-model="selectedTWater" button button-variant="outline-light">
                          T
                        </b-form-checkbox>
                        <b-form-checkbox v-model="selectedWWater" button button-variant="outline-light">
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
                          v-model="height"
                          :options="heights"
                          buttons
                          button-variant="dark"
                          size="lg"
                          name="buttons-2"
                      ></b-form-checkbox-group>
                    </div>
                  </b-form-group>

                  <b-form-group>
                    <b-card-title align="left" class="title">Weight</b-card-title>
                    <div>
                      <b-form-checkbox-group
                          v-model="selected"
                          :options="weights"
                          buttons
                          button-variant="dark"
                          size="lg"
                          name="buttons-2"
                      ></b-form-checkbox-group>
                    </div>
                  </b-form-group>
                  <div class="searchButton">
                    <b-button v-on="onClick">Search
                      <b-icon icon="search" size="sm" class="iconSearch"></b-icon>
                    </b-button>
                  </div>
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
  name: "Options",
  data() {
    return {

      selected: [],
      "height": [],
      selectedAbility: [],
      selectedTBug: [],
      selectedWBug: [],
      selectedTDragon: [],
      selectedWDragon: [],
      selectedTFairy: [],
      selectedWFairy: [],
      selectedTFire: [],
      selectedWFire: [],
      selectedTGhost: [],
      selectedWGhost: [],
      selectedTGround: [],
      selectedWGround: [],
      selectedTNormal: [],
      selectedWNormal: [],
      selectedTPsychic: [],
      selectedWPsychic: [],
      selectedTSteel: [],
      selectedWSteel: [],
      selectedTDark: [],
      selectedWDark: [],
      selectedTElectric: [],
      selectedWElectric: [],
      selectedTFighting: [],
      selectedWFighting: [],
      selectedTFlying: [],
      selectedW: [],
      selectedTGrass: [],
      selectedWGrass: [],
      selectedTIce: [],
      selectedWIce: [],
      selectedTPoison: [],
      selectedWPoison: [],
      selectedTRock: [],
      selectedWRock: [],
      selectedTWater: [],
      selectedWWater: [],
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
      heights: ["small", "medium", "large"],
      weights: ["light", "normal", "heavy"],
      json: {

      },
    }
  },
  methods: {
    onClick(event) {
      event.preventDefault();
      this.$emit('submit');
    },
  }
}

</script>

<style>
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
  margin: 8px 0 28px !important;
}

.marginType {
  margin-left: 40px;
  margin-bottom: 40px;
}

.marginleft {
  margin-left: 40px;
}

.dropdown-menu {
  max-height: 280px;
  overflow-y: auto;
}

.dropdown-toggle::after {
  margin-left: 200px !important;
}

.custom-select {
  padding: 0.375rem 160px 0.375rem 0.75rem !important;
}

.searchButton {
  margin-top: 130px !important;
  margin-left: 280px !important;
}

.iconSearch {
  margin-left: 16px;
}

</style>