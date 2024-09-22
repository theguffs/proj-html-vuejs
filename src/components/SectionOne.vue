<script>
export default {
  data() {
    return {
      
  }
}
};
</script>

<template>

<section class="bg">
  <div class="container-fluid">
    <div class="row">
      <!--parte a SINISTRA-->
      <div class="col-5 left text-left">
        <p class="left-text1">New challenge, new skills</p>
        <p class="left-text2"><strong>BUILD YOUR OWN <br>LIFE COACHING <br> BUSINESS</strong></p>
        <p class="left-text3">Whole-life Business Coaching for committed <br> entrepreneus</p>
        <button>
          Get started today
        </button>
      </div>

      <!--parte a DESTRA-->
      <div class="globo-container col">
        <img src="../assets/business/images/home-business-hero-global-image.png" alt="Mappamondo che gira" class="globo-rotante">
        <img src="../assets/business/images/home-business-hero-avatar.png" alt="hero" class="hero-image">
      </div>
    </div>
  </div>
</section>
</template>

<style scoped>

/* parte a sinistra*/

.bg{
  background-color: #eceeef;
}
.left{
  padding-left: 150px;
}
.left-text1{
  color: #61e6d2;
  font-size: 1.8rem;
  padding-top: 100px;
  padding-left: 150px;
}
.left-text2{
  font-size: 3rem;
  padding-left: 150px;
}
.left-text3{
 padding-left: 150px;
}
button{
  background-color:#61e6d2 ;
  color: white;
  padding:10px 25px;
  border: 0;
  border-radius: 10px;
  margin-left: 150px ;
}

/* parte a destra*/

.globo-container {
  width: 100%; 
  height: 100%; 
  position: relative;
  overflow: hidden; /* nasconde l'immagine fuori dal contenitore */
 
}
.hero-image {
  position: absolute; 
  top: 50%; 
  left: 50%; 
  transform: translate(-50%, -50%); /* centra esattamente */
  height: 100%;
  z-index: 10; /* Porta l'immagine in primo piano */
}

.globo-rotante {
  animation: rotazione-globo 10s linear infinite;
}

@keyframes rotazione-globo {
  from {
    transform: rotate(360deg);
  }
  to {
    transform: rotate(0deg);
  }
}
</style>