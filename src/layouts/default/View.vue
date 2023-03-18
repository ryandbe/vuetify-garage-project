<template>
  <v-main>
    <router-view />
  </v-main>
</template>

<script lang="ts" setup>

import { onMounted } from 'vue';

onMounted(() => {
  console.log('View mounted.')
})

</script>
