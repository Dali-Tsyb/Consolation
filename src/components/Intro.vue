<script setup></script>

<template>
   <div class="intro">
      <div class="intro-brand">CONSOLATION</div>
      <div class="intro-text">Ароматы для спокойствия души</div>
   </div>
</template>

<style scoped>
.intro {
   height: 100vh;
   display: flex;
   flex-direction: column;
   justify-content: center;
   align-items: center;
   padding-top: 2vw;
}
.intro-brand {
   font-family: ztchablis;
   font-size: 6vw;
   color: #1b1b1b;
   opacity: 0;
   animation: fadeIn 1.3s ease-in-out forwards;
}
@keyframes fadeIn {
   0% {
      opacity: 0;
   }
   100% {
      opacity: 1;
   }
}
.intro-text {
   font-family: misskatherine;
   font-size: 7vw;
   color: #1b1b1b;
   position: relative;
   overflow: hidden;
}
.intro-text::before {
   content: "";
   position: absolute;
   top: 0;
   left: -50%;
   width: 200vh;
   height: 100%;
   background: linear-gradient(to left, #fafafa 90%, #9f484800);
   animation: handwriting 9s 1s ease-in-out forwards;
}
@keyframes handwriting {
   0% {
      transform: translateX(0);
   }
   50% {
      transform: translateX(100%);
   }
   100% {
      transform: translateX(200%);
   }
}

@media (width < 550px) {
   .intro {
      .intro-brand {
         font-size: 12vw;
      }
      .intro-text {
         font-size: 15vw;
      }
   }
}
</style>
