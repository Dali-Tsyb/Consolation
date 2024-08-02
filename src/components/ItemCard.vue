<script setup>
defineProps({
   name: String,
   text: String,
   price: Number,
   img: String,
   onClickAdd: Function,
});
</script>

<template>
   <div class="item-card">
      <div class="item-name">{{ name }}</div>
      <div class="item-text">{{ text }}</div>
      <div class="item-price">{{ price }} руб.</div>
      <div @click="onClickAdd" class="item-button">КУПИТЬ</div>
      <div class="item-img"><img :src="img" alt="candle" /></div>
   </div>
</template>

<style scoped>
.item-card {
   display: grid;
   grid-template-columns: 45% 55%;
   grid-template-areas:
      "name photo"
      "text photo"
      "price photo"
      "button photo";
   justify-content: center;
   align-items: center;
   gap: 4vw;
   padding: 8vw 0 4vw 12vw;
   height: 100%;
   font-family: montserrat;
   text-align: left;
   background: linear-gradient(#fafafa, rgba(175, 139, 120, 0) 100%);
}
.item-name {
   transform: translateX(-5%);
   grid-area: name;
   font-family: misskatherine;
   font-size: 9vw;
   color: rgb(68, 68, 68);
}
.item-text {
   grid-area: text;
   font-size: 1.5vw;
   color: rgb(66, 65, 65);
}
.item-price {
   grid-area: price;
   margin-top: 1vw;
   font-size: 1.8vw;
   color: rgb(77, 77, 77);
}
.item-button {
   grid-area: button;
   background: white;
   border: 1px solid rgba(0, 0, 0, 0.278);
   border-radius: 100px;
   cursor: pointer;
   width: fit-content;
   height: fit-content;
   padding: 3% 5%;
   letter-spacing: 0.05vw;
   color: rgb(77, 77, 77);
   font-weight: bold;
   font-size: 1.4vw;
   transition: 0.2s;
}
.item-button:hover {
   background: rgb(67, 67, 67);
   color: rgb(190, 190, 190);
}
.item-button:active {
   background: rgb(47, 47, 47);
   color: rgb(156, 156, 156);
}
.item-img {
   grid-area: photo;
   text-align: center;
   img {
      width: 100%;
      scale: 130%;
      transform: translateX(-3%);
   }
}
@media (width < 550px) {
   .item-card {
      grid-template-columns: 1fr;
      grid-template-areas:
         "name"
         "photo"
         "text"
         "price"
         "button";
      text-align: center;
      padding: 0 15vw 4vw 15vw;
      gap: 5vw;
   }
   .item-name {
      font-size: 20vw;
   }
   .item-text {
      font-size: 3.5vw;
   }
   .item-price {
      font-size: 4.6vw;
   }
   .item-button {
      font-size: 4vw;
      justify-self: center;
   }
   .item-img {
      img {
         width: 100%;
         scale: 150%;
         transform: translateX(0%);
         margin-bottom: 3vw;
      }
   }
}
</style>
