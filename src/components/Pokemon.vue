<template>
  <div class="w-50 p-3 mb-1 mx-auto">
    <b-card title="Card Title" body-class="text-center" header-tag="nav" id="card">
      <template #header>
        <b-nav card-header tabs>
          <b-nav-item active>Active</b-nav-item>
          <b-nav-item>Inactive</b-nav-item>
          <b-nav-item disabled>Disabled</b-nav-item>
        </b-nav>
      </template>

      <b-card-text>
        With supporting text below as a natural lead-in to additional content.
      </b-card-text>

      <b-button variant="primary">Go somewhere</b-button>
    </b-card>
  </div>
</template>

<script>
export default {
  name: "Pokemon",
  props: {
    content: undefined,
    number: Number,
  }
}

</script>

<style>
 #card {
   padding:10px 40px 40px 40px !important;
   background-color: #29292F !important;
   border-radius: 8px;
 }
</style>