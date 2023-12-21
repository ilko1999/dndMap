<script setup lang="ts">
import { defineProps } from 'vue/dist/vue.js';
import { cn } from '../../lib/utils';
import { computed } from 'vue';
import { HtmlHTMLAttributes } from 'vue/dist/vue.js';

interface Props extends /* @vue-ignore */ HtmlHTMLAttributes {
  className?: string;
}

const props = defineProps<Props>();

const containerclass = computed(() => {
  return 'mb-1 font-medium leading-none tracking-tight';
});
</script>

<template>
  <h5 :class="cn(containerclass, props.className)" />
</template>
