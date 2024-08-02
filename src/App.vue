<script setup>
import { ref, onMounted, provide, computed } from "vue";
import axios from "axios";

import Drawer from "./components/Drawer.vue";
import Header from "./components/Header.vue";
import Intro from "./components/Intro.vue";
import About from "./components/About.vue";
import ItemList from "./components/ItemList.vue";
import Footer from "./components/Footer.vue";

const items = ref([]);
const cart = ref([]);
const about = ref();
const isOpen = ref(false);
const totalPrice = computed(() => {
   return cart.value.reduce((total, item) => total + item.price, 0);
});

const drawer = computed(() => {
   return {
      isOpen: isOpen.value,
   };
});

onMounted(async () => {
   try {
      const { data } = await axios.get(
         "https://e7c6ac452dabdbf8.mokky.dev/items"
      );
      items.value = data;
   } catch (error) {
      console.log(error);
   }
});

function toggleDrawer() {
   isOpen.value = !isOpen.value;
}

function scrollToAbout() {
   window.scrollTo({
      top: about.value.$el.offsetTop,
      behavior: "smooth",
   });
}

function addToCart(item) {
   cart.value.push(item);
   console.log(cart.value);
}

function removeFromCart(item) {
   cart.value.splice(cart.value.indexOf(item), 1);
}

function emptyCart() {
   cart.value = [];
}

provide("cart", { cart, removeFromCart, totalPrice, emptyCart });
</script>

<template>
   <Drawer :toggleDrawer="toggleDrawer" :drawer="drawer" />
   <Header :toggleDrawer="toggleDrawer" :scrollToAbout="scrollToAbout" />
   <Intro />
   <About ref="about" />
   <ItemList :items="items" @addToCart="addToCart" />
   <Footer />
</template>

<style scoped>
body {
   overflow-x: hidden !important;
}
</style>
