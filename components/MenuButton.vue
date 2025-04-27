<script lang="ts" setup>
import { defineProps } from "vue";

const props = defineProps<{
  isGroup: boolean;
  text: string;
  icon: string;
}>();
</script>

<template>
  <button
    :class="[
      'flex-1 text-white py-4 rounded-[10px] flex items-center justify-center gap-1.5 md:gap-3 text-sm transition lg:w-[200px] border border-[rgba(255,255,255,0.1)]',
      isGroup
        ? 'bg-[#12294A] hover:bg-[#1c3a5c]'
        : 'bg-transparent hover:bg-[#1c3a5c]',
    ]"
  >
    <img :src="icon" :alt="text" class="w-6 h-6"/>
    <span
      class="text-white font-normal text-sm leading-[14px] md:text-base md:leading-[22px]"
      >{{ text }}</span
    >
  </button>
</template>
