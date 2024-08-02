<script setup>
defineProps({
   img: String,
   type: String,
   name: String,
   price: Number,
});

const emit = defineEmits(["onClickRemove"]);
</script>

<template>
   <div class="cart-item">
      <img :src="img" class="cart-item-img" alt="candle" />
      <div class="cart-item-name">{{ type }} "{{ name }}"</div>
      <div class="cart-item-price">{{ price }} руб.</div>
      <img
         @click="emit('onClickRemove')"
         src="/icons/bin.png"
         alt=""
         class="cart-item-button"
      />
   </div>
</template>

<style scoped>
.cart-item {
   display: grid;
   grid-template-columns: 30% 60% 10%;
   grid-template-areas:
      "photo name button"
      "photo price button";
   align-items: center;
   justify-content: center;
   background: #fafafa;
   border: 1px solid rgba(0, 0, 0, 0.165);
   border-radius: 12px;
   padding: 4.5% 4.5% 4.5% 0;
   margin-bottom: 1vw;
   color: rgb(50, 50, 50);
   font-size: 1vw;
}
.cart-item-img {
   grid-area: photo;
   width: 100%;
   scale: 180%;
}
.cart-item-name {
   grid-area: name;
   font-weight: bold;
   margin-bottom: 6%;
}
.cart-item-price {
   grid-area: price;
}
.cart-item-button {
   grid-area: button;
   width: 1.2vw;
   cursor: pointer;
   transition: 0.2s;
   opacity: 60%;
   align-self: end;
   justify-self: end;
}
.cart-item-button:hover {
   opacity: 75%;
}
.cart-item-button:active {
   opacity: 100%;
}
@media (width < 550px) {
   .cart-item {
      grid-template-columns: 35% 60% 5%;
      padding: 6.5% 6.5% 6.5% 1.5%;
      font-size: 2.8vw;
   }
   .cart-item-price {
      font-size: 3.3vw;
   }
   .cart-item-img {
      scale: 230%;
   }
   .cart-item-button {
      width: 3.5vw;
   }
}
</style>
