<template>
  <div id="app">
    <Header />
    <main>
      <Hero />
      <Features />
      <HowDoWeClean />
    </main>
  </div>
</template>

<script>
import Header from "./components/Header.vue"
import Hero from './components/Hero.vue'
import Features from './components/Features.vue'
import HowDoWeClean from './components/HowDoWeClean.vue'

export default {
  name: 'App',
  components: { 
    Header,
    Hero,
    Features,
    HowDoWeClean
  }
}
</script>

<style lang="scss">
  * {
    font-family: 'TTTravels';
    margin: 0;
    padding: 0;
  }

  @font-face {
    font-family: 'TTTravels';
    font-weight: 700;
    src: url('./fonts/TTTravels-Bold.ttf');
  }

  @font-face {
    font-family: 'TTTravels';
    font-weight: 600;
    src: url('./fonts/TTTravels-DemiBold.ttf');
  }

  @font-face {
    font-family: 'TTTravels';
    font-weight: 300;
    src: url('./fonts/TTTravels-Light.ttf');
  }

  @font-face {
    font-family: 'TTTravels';
    font-weight: 400;
    src: url('./fonts/TTTravels-Regular.ttf');
  }

  @font-face {
    font-family: 'TTTravels';
    font-weight: 500;
    src: url('./fonts/TTTravels-Medium.ttf');
  }
</style>
