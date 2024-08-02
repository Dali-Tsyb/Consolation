<script setup>
import { inject} from "vue";

import CartList from "./CartList.vue";

defineProps({
   drawer: Object,
   toggleDrawer: Function,
});

const { totalPrice, emptyCart } = inject("cart");

</script>

<template>
   <div
      @click="toggleDrawer"
      class="bg"
      :class="drawer.isOpen ? 'drawer-open-bg' : 'drawer-closed-bg'"
   ></div>
   <div
      class="cart"
      :class="drawer.isOpen ? 'drawer-open-cart' : 'drawer-closed-cart'"
   >
      <div class="cart-top">
         <img
            @click="toggleDrawer"
            src="/icons/cross.png"
            class="cart-top-button"
            alt="close"
         />
         <div class="cart-top-title">КОРЗИНА</div>
      </div>
      <div class="cart-middle">
         <div class="cart-middle-scroll">
            <CartList />
         </div>
      </div>
      <div class="cart-bottom">
         <div class="cart-bottom-total">
            <span>ИТОГО:</span><span> {{ totalPrice }} руб.</span>
         </div>
         <button class="cart-bottom-button" @click="emptyCart" :disabled="!totalPrice">
            ОФОРМИТЬ ЗАКАЗ
         </button>
      </div>
   </div>
</template>

<style scoped>
.bg {
   z-index: 101;
   background: rgba(0, 0, 0, 0.394);
   position: fixed;
   top: 0;
   left: 0;
   right: 0;
   height: 100%;
   transition: opacity 0.5s;
}
.drawer-open-bg {
   opacity: 100%;
}
.drawer-closed-bg {
   opacity: 0%;
   pointer-events: none;
}
.cart {
   z-index: 102;
   background: #fafafa;
   position: fixed;
   top: 0;
   right: 0;
   height: 100%;
   width: 26%;
   font-family: montserrat;
   color: rgb(62, 62, 62);
   padding: 2vw 0 2vw 2vw;
   transition: transform 0.3s ease-in-out;
}
.drawer-open-cart {
   transform: translateX(0%);
}
.drawer-closed-cart {
   transform: translateX(100%);
}
.cart-top {
   display: flex;
   align-items: center;
   overflow: hidden;
}
.cart-top-button {
   width: 1.5vw;
   opacity: 70%;
   cursor: pointer;
   transition: transform 0.6s ease-out;
}
.cart-top-button:hover {
   transform: rotate(180deg);
}
.cart-top-title {
   width: 100%;
   margin-right: 1.5vw;
   text-align: center;
   font-size: 1.5vw;
   font-weight: bold;
   color: rgb(62, 62, 62);
}
.cart-middle {
   margin-top: 2.2vw;
}
.cart-middle-scroll {
   overflow-y: auto;
   position: relative;
   height: 60vh;
}
.cart-bottom {
   position: absolute;
   bottom: 0;
   left: 0;
   right: 0;
   display: flex;
   flex-direction: column;
   align-items: center;
   justify-content: center;
   gap: 2vw;
   padding: 1.5vw 1.2vw;
   background: #fafafa;
   border-top: 1px solid rgba(0, 0, 0, 0.165);
   height: 25vh;
}
.cart-bottom-total {
   display: flex;
   justify-content: space-between;
   width: 100%;
   font-size: 1.3vw;
   font-weight: bold;
}
.cart-bottom-button {
   width: 100%;
   font-family: montserrat;
   color: rgb(223, 223, 223);
   font-size: 1.3vw;
   border: none;
   border-radius: 100px;
   background: #2c2c2c;
   padding: 5% 6%;
   cursor: pointer;
   transition: background 0.1s;
}
.cart-bottom-button:hover {
   background: rgb(57, 57, 57);
}
.cart-bottom-button:active {
   background: rgb(43, 43, 43);
}
.cart-bottom-button:disabled {
   background: rgb(127, 127, 127);
   pointer-events: none;
}
@media (width < 550px) {
   .cart {
      width: 60%;
      padding: 4vw;
   }
   .cart-top-title {
      font-size: 4vw;
   }
   .cart-top-button {
      width: 3.4vw;
   }
   .cart-middle-scroll {
      height: 70vh;
   }
   .cart-bottom {
      gap: 6vw;
      padding: 0 4vw;
      height: 20vh;
   }
   .cart-bottom-total {
      font-size: 4vw;
   }
   .cart-bottom-button {
      font-size: 3.5vw;
   }
}
</style>
