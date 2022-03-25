<template>
  <section class="hero">
    <div class="container">
      <div class="image-container">
              <img src="../assets/images/headshot.jpg" alt="Ken Taylor on set">
            </div>
      <h1 class="heading">Hello! <span class="break">My name is <span class="name">Ken.</span></span></h1>
    </div>
  </section>

  
</template>

<script>
  import {gsap} from 'gsap';

export default {

  mounted() {
    setTimeout(() => {
      this.fadeIn()
    }, 1000)
  },

  methods: {
    fadeIn() {
      // const gsap = this.$gsap
      gsap.to('.image-container', { duration: 1.5, opacity: 1,})
      gsap.to('.heading', { duration: 1, y: 0, opacity: 1,}, "<")
      gsap.to('.name', { duration: 1, opacity: 1,}, ">-o.5")
    }
  }

}
</script>

<style lang="scss">
@import '~/assets/scss/variables';

  .hero {
    height: 100%;
    width: 100vw;
    background-color: $green;
  }
  
  .container {
    width: 100%;
    height: 100%; 
    display: flex;
    justify-content: center;
    align-items: center;
    max-width: 1200px;
    margin: 0 auto;

  }

  .image-container {
    max-width: 300px;
    height: auto;
    opacity: 0;
    display: flex;
    -webkit-box-shadow: -37px 24px 50px -1px rgba(0,0,0,0.48); 
    box-shadow: -37px 24px 50px -1px rgba(0,0,0,0.48);

    img {
      width: 100%;
      height: 100%;
    }
    @include tablet-up {
      max-width: 300px;
    }
    // transform: translateX(100px)
}

.heading {
  font-size: 5.5rem;
  color: white;
  line-height: 1;
  padding-left: 40px;
  opacity: 0;
  transform: translateY(-20px);

  .break {
    display: block;

    span {
      color: $orange;
      opacity: 0;
    }
  }

}

img {
  width: 100%;    
}

</style>

