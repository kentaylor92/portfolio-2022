<template>
  <section class="app">
      <div class="app-container">
        <div class="icons">          
        </div>
        <div class="snap">
          <Hero />
        </div>
        <div class=snap>
          <About />
        </div>
       

      </div>
  </section>
</template>

<script>

export default {

}
</script>

<style lang="scss">
@import '~/assets/scss/variables';

.app-container {
  position: relative;
  height: 100vh;
  width: 100vw;
  overflow: auto;
  scroll-snap-type: y mandatory;
}

.snap {
  display: flex;
  justify-content: center;
  align-items: center;
  height: 100vh;
  scroll-snap-align: center;
}

</style>