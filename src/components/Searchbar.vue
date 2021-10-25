<template>
  <div>
    <h1>{{ msg }}</h1>
    <div class="w-50 p-3 mb-1 mx-auto">
      <b-form-input v-model="text" placeholder="Search for for Pokemon" id="searchbar">
      </b-form-input>
    </div>
  </div>
</template>

<script>
export default {
  name: 'Searchbar',
  props: {
    msg: String
  }
}
</script>

<style>
#searchbar {
  -webkit-border-radius: 20px;
  -moz-border-radius: 20px;
  border-radius: 50px;
  background-color: #29292F;
  border-color: #29292F;
}

</style>