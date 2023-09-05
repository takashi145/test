<script setup lang="ts">
import { ref } from 'vue';
import Card from './components/Card.vue';
import Footer from './components/Footer.vue';

interface Item {
  url: string
  image: string
  title: string
}

const items = ref<Item[]>([
  {
    "url": "/",
    "image": "/public/images/app-name-generator.PNG",
    "title": "AppNameGenerator"
  },
  {
    "url": "/",
    "image": "/public/images/glossary-app.PNG",
    "title": "用語集アプリ"
  },
  {
    "url": "/",
    "image": "/public/images/noutore1.PNG",
    "title": "脳トレタイピング"
  },
  {
    "url": "/",
    "image": "/public/images/sharer.PNG",
    "title": "Sharer"
  },
  {
    "url": "/",
    "image": "/public/images/timetable.PNG",
    "title": "TimeTable"
  }
]);
</script>

<template>
  <div class="bg-gray-100 dark:bg-gray-800 min-h-screen">
    <div class="pt-8 max-w-7xl mx-auto">
      <div class="flex flex-col md:flex-row justify-center md:justify-start md:pl-8 items-center">
        <img 
          src="https://avatars.githubusercontent.com/u/84027833?s=400&u=2a47f99db63cdd16478f99daa60b84978ab44c85&v=4"
          alt="takashi145"
          class="w-24 h-24 rounded-full"
        />
        <span class="ml-3 text-lg text-gray-600 dark:text-white">takashi145</span>
      </div>

      <div class="p-8 sm:columns-2 md:columns-3">
        <div 
          v-for="(item, index) in items" 
          :key="index" 
          class="mb-8 max-w-lg mx-auto"
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
