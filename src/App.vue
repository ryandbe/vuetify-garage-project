<template>
  <router-view />
</template>

<script lang="ts" setup>

import { onMounted } from 'vue';

onMounted(() => {
  console.log('App mounted.')
})

</script>
