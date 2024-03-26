<template>
  <div class="background-layer">
    <img id="background-image" src="https://www.teamhitless.com/wp-content/uploads/2022/11/zeldabg.jpg" alt="">
  </div>
  <HeaderNav/>
  <div class="content">
    <Sorters/>
    <CardDisplay/>
  </div>
  <Footer/>
</template>
<script>

import HeaderNav from './components/HeaderNav.vue'
import Footer from './components/Footer.vue'
import Card from './components/Card.vue'
import CardDisplay from './components/CardDisplay.vue'
import Sorters from './components/Sorters.vue'


export default {
  name: 'App',
  components: {
    HeaderNav,
    Footer,
    Card,
    CardDisplay,
    Sorters,
  },
  methods: {

  },
  created() {
    
  },
  mounted() {

  },
}
</script>

<style>
@import './styles/appStyles.css';
</style>
