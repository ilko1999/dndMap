<script setup lang="ts">
import HelloWorld from './components/HelloWorld.vue';
import { MyButton } from './components';
</script>

<template>
  <h1 class="text-xl hover:underline hover:text-accent">Hello</h1>
  <button class="text-lg hover:text-primary">Navigate to about page</button>
  <HelloWorld :msg="'Hello'"></HelloWorld>
  <MyButton>asdasdasdasd</MyButton>
</template>
