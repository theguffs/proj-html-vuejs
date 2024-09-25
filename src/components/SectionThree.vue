<script>
export default {
  data() {
    return {
      currentIndex: 0,
      carouselItems: [
        {
          image: '/public/carusel1/home-business-service-slide-01-480x298.jpg',
          title: 'Consultative Training',
          description: 'With a coach addressing multiple issues that are off balance, affecting your business in various unconsidered ways.'
        },
        {
          image: '/public/carusel1/home-business-service-slide-02-480x298.jpg', 
          title: 'Real Deal Coaching',
          description: 'Brings an exceptionally powerful opportunity. Being able to accept, to work with that opportunity.'
        },
        {
          image: '/public/carusel1/home-business-service-slide-03-480x298.jpg', 
          title: 'Advisor Training Program',
          description: 'Getting high quality, entrepreneur mindset driven online business coaching, is what is needed.'
        }
      ]
    }
  },
}
</script>

<template>
<section class="bg">
  <div class="container">
    <div class="row">
      <div class="col text-center">
        <p class="left-text1">Let’s Dream Big Together</p>
        <p class="left-text2">Explore How can I help you</p>
      </div>
    </div>
    <div class="row">
      <div v-for="(item, i) in carouselItems" class="card" :key="i">
        <img :src="item.image" :alt="item.title" >
        <div class="card-info">
          <h5 class="card-title">{{item.title}}</h5>
          <p class="card-text">{{item.description}}</p>
        </div>
        <div class="discover">
          Discover now
        </div>
      </div>
    </div>
  </div>
</section>
</template>

<style scoped>
.carousel-inner img {
  height: 500px; 
  object-fit: cover; 
}

.carousel-caption {
  background: rgba(0, 0, 0, 0.5);
  padding: 10px;
}
.card{
  text-align: center;
  padding: 20px;
  margin: 20px;
  width: calc(33% - 40px);
}
.card-info{
  padding: 20px;
}
.discover{
  color: #61e6d2;
  margin-top: 1px solid  #eceeef;
}
</style>