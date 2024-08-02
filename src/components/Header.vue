<script setup>
defineProps({
   scrollToAbout: Function,
   toggleDrawer: Function,
});
function scrollToBottom() {
   window.scrollTo({ top: document.body.scrollHeight, behavior: "smooth" });
}
</script>

<template>
   <div class="header">
      <div class="header-logo">CONSOLATION</div>
      <div class="header-menu">
         <div @click="scrollToAbout" class="header-menu-about">О НАС</div>
         <div @click="scrollToBottom" class="header-menu-contacts">
            КОНТАКТЫ
         </div>
         <img
            @click="toggleDrawer"
            src="/icons/cart.png"
            class="header-menu-cart"
            alt="cart"
         />
      </div>
   </div>
</template>

<style scoped>
.header {
   z-index: 100;
   background: #2c2c2c;
   font-family: Montserrat;
   color: #f1f1f1;
   position: fixed;
   left: 0;
   right: 0;
   display: flex;
   justify-content: space-between;
   align-items: center;
   padding: 0.5vw 1vw;
   height: fit-content;
}
.header-logo {
   font-family: ZtChablis;
   font-size: 2vw;
   cursor: pointer;
}
.header-menu {
   font-size: 1vw;
   color: #dcdcdc;
   display: flex;
   gap: 2vw;
   align-items: center;
}
.header-menu > * {
   cursor: pointer;
   transition: 0.2s;
}
.header-menu-cart {
   width: 1.3vw;
   opacity: 80%;
}
.header-menu-about:hover,
.header-menu-contacts:hover,
.header-menu-cart:hover {
   opacity: 60%;
}
.header-menu-about:active,
.header-menu-contacts:active,
.header-menu-cart:active {
   opacity: 40%;
}

@media (width < 550px) {
   .header {
      padding: 1vw 0 2vw 0;
      flex-direction: column;
      gap: 2vw;
      .header-logo {
         font-size: 7vw;
      }
      .header-menu {
         font-size: 3.6vw;
         gap: 4vw;
      }
      .header-menu-cart {
         width: 4vw;
      }
   }
}
</style>
