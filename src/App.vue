<template>
  <div class="app">
      <Header />
      <Booking />
 
      



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


  }
}
</script>

<style lang="scss">
@import './styles/global.scss'

</style>
