<template>
  <v-app>
    <default-bar />

    <default-view />
  </v-app>
</template>

<script lang="ts" setup>

import DefaultBar from './AppBar.vue'
import DefaultView from './View.vue'
import { onMounted } from 'vue';

onMounted(() => {
  console.log('Default mounted.')
})

</script>
