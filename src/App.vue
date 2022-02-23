<template>
  <div class="app">
      <Header :scrolling="scrollPosition" :smartClass="smartHeaderClass"/>
      <Booking :scrolling="scrollPosition" :smartClass="smartClass" @removeSmartClass="removeSmart"/>

      <Jumbotron :scrolling="scrollPosition"/>



  </div>
</template>

<script>
import Header from '@/components/Header';
import Booking from '@/components/Booking';
import Jumbotron from '@/components/Jumbotron';


export default {
  
  name: 'App',
  components: {
      Header,
      Booking,
      Jumbotron
  },

  data() {
    return {
      scrollPosition: 0,
      smartClass: false,
      smartHeaderClass: false,
    }
  },
  
  methods: {
    updateScroll() {
      if (this.scrollPosition > 20) {
        this.smartClass = true
        this.smartHeaderClass = false
      } else if (this.scrollPosition <= 20 || this.scrollPosition === 0) {
        this.smartClass = false
      }
      this.scrollPosition = window.scrollY;
    },

    removeSmart() {
      this.smartClass = false
      console.log(this.smartClass);
      this.smartHeaderClass = true
    }
  },
  
  mounted() {
    window.addEventListener('scroll', this.updateScroll);
  }


}
</script>

<style lang="scss">
@import './styles/global.scss';

</style>
