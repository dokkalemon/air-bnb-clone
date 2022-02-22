<template>
  <div class="app">
      <Header :scrolling="scrollPosition"/>
      <Booking :scrolling="scrollPosition"/>



  </div>
</template>

<script>
import Header from '@/components/Header';
import Booking from '@/components/Booking';


export default {
  
  name: 'App',
  components: {
      Header,
      Booking,
  },

  data() {
    return {
      scrollPosition: 0,
    }
  },
  
  methods: {
    updateScroll() {
      this.scrollPosition = window.scrollY;
    }
  },
  
  mounted() {
    window.addEventListener('scroll', this.updateScroll);
  }


}
</script>

<style lang="scss">
@import './styles/global.scss'

</style>
