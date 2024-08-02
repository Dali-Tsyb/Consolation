<script setup>
import { ref, computed } from "vue";
import "vue3-carousel/dist/carousel.css";
import { Carousel, Slide, Pagination, Navigation } from "vue3-carousel";

import ItemCard from "./ItemCard.vue";

defineProps({
   items: Array,
});

const emit = defineEmits(["addToCart"]);

const bgColors = [
   "rgb(255, 226, 152)",
   "rgb(204, 134, 134)",
   "rgb(149, 149, 149)",
   "rgb(246, 185, 209)",
   "rgb(169, 185, 246)",
   "rgb(175, 139, 120)",
   "rgb(255, 226, 152)",
];

const currentSlide = ref(0);

const backgroundColor = computed(() => {
   if (currentSlide.value === -1) {
      return bgColors[bgColors.length - 2];
   } else {
      return bgColors[currentSlide.value];
   }
});

const updateCurrentSlide = (event) => {
   currentSlide.value = event.slidingToIndex;
   console.log(currentSlide.value);
};
</script>

<template>
   <div class="item-list">
      <Carousel
         :wrapAround="true"
         :transition="600"
         @slide-start="updateCurrentSlide"
         :style="{
            backgroundColor: backgroundColor,
            transition: 'background-color 1s',
            paddingBottom: '5vh',
            overflow: 'hidden',
         }"
      >
         <Slide v-for="item in items" :key="item.id">
            <ItemCard
               :name="item.name"
               :text="item.text"
               :price="item.price"
               :img="item.img"
               :onClickAdd="() => emit('addToCart', item)"
            />
         </Slide>
         <template #addons>
            <Navigation />
            <Pagination />
         </template>
      </Carousel>
   </div>
</template>

<style scoped>
Carousel {
   transform: scale(30%);
}
</style>
