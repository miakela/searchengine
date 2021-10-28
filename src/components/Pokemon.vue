<template>
  <div class="w-75 p-3 mb-1 mx-auto">
    <b-card body-class="text-center" header-tag="nav">
      <template #header>
        <b-nav card-header tabs>
          <b-nav-item active>Info</b-nav-item>
          <b-nav-item>Stats</b-nav-item>
          <b-nav-item>Evolutions</b-nav-item>
        </b-nav>
      </template>
      <b-row no-gutters>
        <b-col md="3">
          <b-card-img :src="imgsrc" rounded-0 class="img"></b-card-img>
        </b-col>
        <b-col md="6">
          <b-card-body>
            <b-card-text>
              This is a wider card with supporting text as a natural lead-in to additional content.
              This content is a little bit longer.
            </b-card-text>
          </b-card-body>
        </b-col>
      </b-row>
    </b-card>
  </div>
</template>

<script>
export default {
  name: "Pokemon",
  props: {
    pokemonname: String,
    number: Number,
    imgsrc: String,
  }
}

</script>

<style>
.card-body.text-center {
  padding: 10px 40px 40px 40px !important;
  background-color: #29292F !important;
  border-radius: 0 0 8px 8px;
}

.nav-link.active {
  color: #ffffff !important;
  background-color: #29292F !important;
  border-color: #29292F !important;
}

.card-header {
  background-color: #161618;
  border-radius: 8px 8px 0 0 !important;
}
.img {
  margin-top: 40px;
}
</style>