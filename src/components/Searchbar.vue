<template>
    <div class="w-50 p-3 mb-1 mx-auto">
      <b-form-input v-on:keyup.enter="onSubmit"
                    placeholder="Search for for Pokemon"
                    id="searchbar"
                    :value="value"
                    @input="onQueryInput">

      </b-form-input>
    </div>
</template>

<script>
export default {
  props: {
    value: String
  },

  methods:{
    onSubmit(event) {
      event.preventDefault();
      this.$emit('submit');
    },
    onQueryInput(event){
      this.$emit('input', event)
    }
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