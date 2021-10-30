<template>
  <div>
    <b-button v-b-toggle.sidebar-1>Toggle Sidebar</b-button>
    <b-sidebar id="sidebar-1" title="Filter" bg-variant="dark" text-variant="light">
      <div class="px-3 py-2">
        <template>
        <b-list-group horizontal>
          <b-list-group-item href="#">Cras justo odio</b-list-group-item>
          <b-list-group-item href="#">Dapibus ac facilisis in</b-list-group-item>
          <b-list-group-item href="#">Vestibulum at eros</b-list-group-item>
        </b-list-group>
        </template>
        <b-img src="https://picsum.photos/500/500/?image=54" fluid thumbnail></b-img>
      </div>
    </b-sidebar>
  </div>
</template>

<script>
export default {
  name: "Options",

  data() {
    return {
      items: [
        { age: 40, first_name: 'Dickerson', last_name: 'Macdonald' },
        { age: 21, first_name: 'Larsen', last_name: 'Shaw' },
        {
          age: 89,
          first_name: 'Geneva',
          last_name: 'Wilson',
          _rowVariant: 'danger'
        },
        {
          age: 40,
          first_name: 'Thor',
          last_name: 'MacDonald',
          _cellVariants: { age: 'info', first_name: 'warning' }
        },
        { age: 29, first_name: 'Dick', last_name: 'Dunlap' }
      ]
    }
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

</style>