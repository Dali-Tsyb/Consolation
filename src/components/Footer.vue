<script setup>
const scrollToTop = () => {
   window.scrollTo({ top: 0, behavior: "smooth" });
};
</script>

<template>
   <footer>
      <div class="footer-brand">CONSOLATION</div>
      <div class="footer-socials">
         <div class="footer-socials-inst">
            <img src="/icons/inst.png" alt="inst" />
         </div>
         <div class="footer-socials-vk">
            <img src="/icons/vk.png" alt="vk" />
         </div>
      </div>
      <div class="footer-contacts">
         <div class="footer-contacts-phone">+7 919 ХХХ ХХ ХХ</div>
         <div class="footer-contacts-email">consolation@gmail.com</div>
      </div>
      <div class="footer-button" @click="scrollToTop">
         <span>НАВЕРХ</span> <img src="/icons/arrow.png" alt="arrow" />
      </div>
   </footer>
</template>

<style scoped>
footer {
   height: fit-content;
   background: #2c2c2c;
   font-family: montserrat;
   color: white;
   display: flex;
   flex-direction: column;
   justify-content: center;
   align-items: center;
   padding: 3vw;
   gap: 1vw;
}
.footer-brand {
   font-family: ztchablis;
   font-size: 2.7vw;
   margin-bottom: 1vw;
}
.footer-socials {
   display: flex;
   gap: 1vw;
   div {
      transition: 0.2s;
   }
   img {
      width: 2.4vw;
      opacity: 96%;
      cursor: pointer;
   }
}
.footer-contacts {
   text-align: center;
   margin-bottom: 1vw;
   font-size: 1.1vw;
   color: rgb(221, 221, 221);
}
.footer-button {
   display: flex;
   align-items: center;
   gap: 0.4vw;
   color: rgb(221, 221, 221);
   cursor: pointer;
   transition: 0.2s;
   font-size: 1.2vw;
   img {
      width: 1.03vw;
      filter: invert();
      opacity: 70%;
   }
}
.footer-socials-inst:hover,
.footer-socials-vk:hover,
.footer-button:hover {
   opacity: 80%;
}
.footer-socials-inst:active,
.footer-socials-vk:active,
.footer-button:active {
   opacity: 60%;
}
@media (width < 550px) {
   footer {
      padding: 4vw 0;
   }
   .footer-brand {
      font-size: 3.6vw;
   }
   .footer-socials {
      gap: 3vw;
      img {
         width: 6vw;
      }
   }
   .footer-contacts {
      font-size: 2.4vw;
   }
   .footer-button {
      font-size: 2.7vw;
      img {
         width: 2.4vw;
      }
   }
}
</style>
