<template>
  <div class="basic-layout" :layout-theme="theme">
    <slot></slot>
  </div>
</template>

<script setup lang="ts">
import { toRefs } from "vue";

interface IProps {
  theme?: string;
}
const props = defineProps<IProps>();
const { theme } = toRefs(props); // 구조분해하기
</script>

<style lang="scss" scoped>
.basic-layout {
  display: flex;
  align-items: center;
  justify-content: center;

  padding: 20px;

  background-color: $color-white-000;
  border-radius: 24px;

  &[layout-theme="blue"] {
    background-color: $color-blue-000;
  }
}
</style>
