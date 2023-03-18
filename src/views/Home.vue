<template>
  <MyGarage />
</template>

<script lang="ts" setup>

import MyGarage from '@/components/MyGarage.vue';
import { onMounted } from 'vue';

onMounted(() => {
  console.log('Home mounted.')
})

</script>
