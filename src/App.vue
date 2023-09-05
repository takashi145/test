<script setup lang="ts">
import { onMounted, ref } from 'vue';
import Card from './components/Card.vue';
import Footer from './components/Footer.vue';

interface Item {
  url: string
  image: string
  title: string
}

const items = ref<Item[]>([]);

const fetchItems = async () => {
  const response = await fetch('/src/data/items.json');
  const data = await response.json();
  return data;
}

onMounted(async () => {
  items.value = await fetchItems();
});
</script>

<template>
  <div class="bg-white dark:bg-gray-800 min-h-screen">
    <div class="py-12 px-8">
      <div class="sm:columns-2 md:columns-3">
        <div 
          v-for="(item, index) in items" 
          :key="index" 
          class="mx-2 mb-8 max-w-lg"
        >
          <Card 
            :url="item.url" 
            :image="item.image"
            :title="item.title"
          />
        </div>
      </div>  
    </div>

    <Footer />
  </div>
</template>
