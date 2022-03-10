<template>
  <section class="hero">
    <div class="container">
      <div class="image-container">
              <img src="../assets/images/me2.jpg" alt="Ken Taylor on set">
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
    max-width: 600px;
    opacity: 0;
    // transform: translateX(100px)
}

.heading {
  font-size: 6rem;
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

