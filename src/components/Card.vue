<script setup lang="ts">
interface Props {
  url: string
  image: string
  title: string
}

const props = defineProps<Props>();
</script>
<template>
  <div class="max-w-sm mx-auto border border-gray-600 group/card transform transition-all duration-500 hover:scale-105 shadow-lg overflow-hidden hover:rounded-lg hover:ring-2">
    <img :src="props.image" alt="" class="w-full">
    <a :href="props.url" class="absolute block inset-0 group-hover/card:bg-black group-hover/card:bg-opacity-60 transition-all delay-150">
      <h4 class="absolute bottom-0 p-3 font-semibold text-lg hidden group-hover/card:block text-white w-full">{{ props.title }}</h4>
    </a>
  </div>
</template>