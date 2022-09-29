<template>
  <button class="CustomButton" @click="onClick" :data-href="props.url">
    <slot />
  </button>
</template>

<script setup lang="ts">
import { withDefaults, defineProps } from 'vue';

interface Props {
  url: string;
}

const props = withDefaults(defineProps<Props>(), { url: '/' });

const onClick = () => {
  window.location.assign(props.url);
};
</script>

<style lang="css" scoped></style>
