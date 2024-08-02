<script setup></script>

<template>
   <div class="about">
      <div class="about-title">Что такое свечи <span>consolation</span> ?</div>
      <div class="about-text">
         Давно известно, что ароматерапия и создание уюта вокруг себя помогают
         справляться со стрессом, приносят умиротворение и расслабление, поэтому
         иногда просто необходимо остаться дома и отвлечься от ежедневной суеты.
         <span>Consolation</span> - это линейка ароматических свечей, которые
         помогут вам в такие моменты создать вокруг себя нужную атмосферу. Наши
         свечи сделаны из натурального воска, а каждый аромат тщательно
         подобран, чтобы вы не могли отличить его от природного, ведь именно
         природа является главным источником силы и баланса.
         <p>Выбери аромат, который подходит именно тебе.</p>
      </div>
   </div>
</template>

<style scoped>
.about {
   height: 100vh;
   font-family: montserrat;
   color: rgb(63, 63, 63);
   display: flex;
   flex-direction: column;
   justify-content: center;
   padding: 0 10vw;
}
.about-title {
   font-size: 3.5vw;
   margin-bottom: 7vw;
   span {
      font-family: ztchablis;
      font-size: 4.7vw;
   }
}
.about-text {
   font-size: 1.6vw;
   span {
      font-family: ztchablis;
      font-size: 2.1vw;
      line-height: 2vw;
   }
   p {
      margin-top: 5vw;
   }
}

@media (width < 550px) {
   .about {
      .about-title {
         font-size: 6vw;
         span {
            font-size: 7.3vw;
         }
      }
      .about-text {
         font-size: 3.6vw;
         span {
            font-size: 4.7vw;
         }
      }
   }
}
</style>
