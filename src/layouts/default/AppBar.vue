<template>
  <v-app-bar flat>
    <v-app-bar-title>
      <v-app-bar-nav-icon />
      My Garage
    </v-app-bar-title>

    <!-- {{ count }} -->

    <v-responsive class="mx-auto" max-width="344">
      <v-text-field v-model="searchString" label="Search" placeholder="Enter Search String"
        hide-details="auto"></v-text-field>
    </v-responsive>

    <template v-slot:append>
      <v-btn icon="mdi-magnify" @click="searchIconClicked"></v-btn>
    </template>

  </v-app-bar>
</template>

<script lang="ts" setup>

import { ref, onMounted } from 'vue';

//reactive state
//const count = ref(0);
const searchString = ref("");

//function to mutate state and trigger updates
function searchIconClicked() {
  //count.value++;
  console.log(searchString.value);
}

//lifecycle hooks
onMounted(() => {
  //console.log(`The initial count is ${count.value}.`);
  console.log("AppBar mounted");
  console.log(`The initial search string is ${searchString.value}.`);
})

</script>
