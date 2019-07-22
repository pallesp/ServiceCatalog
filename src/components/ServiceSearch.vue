<template>
  <v-toolbar
    dark
    color="teal"
  >
    <v-toolbar-title>Search Service Catalog</v-toolbar-title>
    <v-autocomplete
      v-model="select"
      :loading="loading"
      :items="items"
      :search-input.sync="search"
      cache-items
      class="mx-3"
      flat
      hide-no-data
      hide-details
      label="Search Service, CTI"
      solo-inverted
    ></v-autocomplete>
    <v-btn icon>
      <v-icon></v-icon>
    </v-btn>
  </v-toolbar>
</template>
<script>
export default {
    name: 'ServiceSearch',
};
</script>

<style scoped>
</style>
