<script setup>
import { inject } from "vue";

import CartItem from "./CartItem.vue";

const { cart, removeFromCart } = inject("cart");
</script>

<template>
   <div class="cart-list" v-auto-animate>
      <CartItem
         v-for="item in cart"
         :key="item.id"
         :img="item.img"
         :type="item.type"
         :name="item.name"
         :price="item.price"
         @onClickRemove="() => removeFromCart(item)"
      />
   </div>
</template>
