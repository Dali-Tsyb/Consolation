<script setup>
defineProps({
   scrollToAbout: Function,
   toggleDrawer: Function,
});
function scrollToBottom() {
   window.scrollTo({ top: document.body.scrollHeight, behavior: "smooth" });
}
const words = [
   "Люблю тебя, мой милый!",
   "У тебя обязательно все будет хорошо",
   "Я очень сильно соскучилась",
   "Ты такой красивый, вот бы видеть тебя как можно чаще",
   "Я так хочу тебя обнять :(",
   "Я думаю о тебе почти 24/7..",
   "Ты самый лучший мальчик на свете <3",
   "Завидую всем кто видит тебя каждый день:(",
   "Я всегда буду рядом с тобой, котенок",
   "Улыбнись!!",
   "Ты - лучик света",
   "Мне так сильно тебя не хватает",
   "Кто прочитал тому запрещается меня игнорить >:(",
   "Я никогда не чувствовала к кому-то так много, поэтому не хочу тебя терять никогда :(",
   "Трудные времена создают сильных котят",
   "Не вешай нос, любимый, у тебя все получится! (И даже если нет - я все равно буду с тобой)",
];
function loveYou() {
   alert(words[Math.floor(Math.random() * words.length)]);
}
</script>

<template>
   <div class="header">
      <div @click="loveYou" class="header-logo">CONSOLATION</div>
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
