<template>
  <div role="alert" :class="cn(containerclass, props.className)">
    <slot></slot>
  </div>
</template>

<script lang="ts">
import { computed } from 'vue';
import { cn } from '../../lib/utils';
import { cva } from 'class-variance-authority';
import { HtmlHTMLAttributes } from 'vue/dist/vue.js';

const containerclass = computed(() => {
  return cva(
    'relative w-full rounded-lg border p-4 [&>svg~*]:pl-7 [&>svg+div]:translate-y-[-3px] [&>svg]:absolute [&>svg]:left-4 [&>svg]:top-4 [&>svg]:text-foreground',
    {
      variants: {
        variant: {
          default: 'bg-background text-foreground',
          destructive:
            'border-destructive/50 text-destructive dark:border-destructive [&>svg]:text-destructive',
        },
      },
      defaultVariants: {
        variant: 'default',
      },
    }
  )({
    variant: props.variant,
  });
});

interface Props extends /* @vue-ignore */ HtmlHTMLAttributes {
  className?: string;
  variant?: 'default';
}

const props = defineProps<Props>();
</script>
