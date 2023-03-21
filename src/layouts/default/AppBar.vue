<template>
  <v-app-bar flat>

    <v-app-bar-nav-icon />

    <v-app-bar-title>My Garage</v-app-bar-title>

    <!-- <v-responsive class="mx-auto" max-width="344">
      <v-text-field v-model="searchString" label="Search" placeholder="Enter Search String"
        hide-details="auto"></v-text-field>
    </v-responsive> -->

    <!-- <template v-slot:append>
      <v-btn icon="mdi-magnify" @click="searchIconClicked"></v-btn>
    </template> -->

    <!-- <v-btn icon="mdi-magnify" @click="searchIconClicked"></v-btn> -->

  </v-app-bar>
</template>

<script lang="ts" setup>

import { ref, onMounted } from 'vue';

//reactive state
const searchString = ref("");

//function to mutate state and trigger updates
function searchIconClicked() {
  console.log(searchString.value);
}

//lifecycle hooks
onMounted(() => {
  console.log("AppBar mounted.");
  console.log(`The initial search string is ${searchString.value}.`);
})

</script>
