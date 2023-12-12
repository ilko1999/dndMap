<template>
  <h1>{{ msg }}</h1>
  <div class="card">
    <VueButton @click="count++">count is {{ count }}</VueButton>
  </div>
</template>

<script setup lang="ts">
import { ref } from 'vue';

defineProps<{ msg: string }>();

const count = ref(0);
</script>
