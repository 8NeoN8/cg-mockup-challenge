<template>
<div id="nav-bar" class="nav-bar sticky">

  <div class="nav-left-side">
    <div class="burger-menu dont-show-big" @click="openSideBar()">
      <i class="fa-solid fa-bars menu-icon dont-show-big"></i>
    </div>
    <div class="logo-display">
      <a href="#">
        <img id="logo-img" src="https://chicksgold.com/logo/chicks-logo-large.svg">
      </a>
    </div>
  </div>

  <div class="nav-middle show-big">
    
    <div class="option-list">
      <template v-for="opt in options" :key="opt">
        <li class="option">
          <div class="option-text" :data-info="opt">
            {{opt}}
          </div>
          <div class="option-arrow">
            <i class="fa-solid fa-angle-down arrow-down"></i>
            <i class="fa-solid fa-angle-up arrow-up"></i>
          </div>
        </li>
      </template>
    </div>
    <div class="middle-cart">
      <div class="currency-display option">
        <div class="currency-text">
          USD
        </div>
        <div class="option-arrow">
            <i class="fa-solid fa-angle-down arrow-down"></i>
            <i class="fa-solid fa-angle-up arrow-up"></i>
          </div>
      </div>
      <div class="cart-button">
        <div class="cart-icon">
          <i class="fa-solid fa-cart-shopping"></i>
        </div>
        <div class="cart-text">
          Cart({{ cartItemCount }})
        </div>
      </div>
    </div>

  </div>

  <div class="nav-right-side">
    <div class="sign-in-button">
      <div class="sign-in-text">
        SIGN IN
      </div>
      <div class="sign-in-icon">
        <i class="fa-solid fa-user"></i>
      </div>
    </div>
  </div>

  <div v-if="sideBarOpen" class="nav-bar-side-menu">
    <div class="top-search-close">

      <button class="close-button" @click="closeSideBar()">
        <div class="close-icon">
          <i class="fa-solid fa-xmark"></i>
        </div>
        <div class="close-text">
          Close
        </div>
      </button>

      <div class="search-bar">

        <div class="search-icon">
          <i class="fa-solid fa-magnifying-glass"></i>
        </div>
        <div class="bar">
          <input type="text" name="bar" id="bar-search" placeholder="Search">
        </div>

      </div>

    </div>
    <div class="side-options">
      <div class="side-option-list">
      <template v-for="opt in sideOptions" :key="opt">
        <li class="side-option">
          <div class="side-option-text" :data-info="opt">
            {{opt}}
          </div>
          <div class="option-arrow">
            <i class="fa-solid fa-caret-down arrow-down"></i>
            <i class="fa-solid fa-caret-up arrow-up"></i>
          </div>
        </li>
      </template>
    </div>
    </div>
  </div>

</div>
</template>

<script>
export default {
  name: 'HeaderNav',
  data() {
    return {
      options: ['CURRENCY', 'ITEMS', 'ACCOUNTS','SERVICES', 'SWAP', 'SELL'],
      sideOptions: ['Currency', 'Items', 'Accounts','Services', 'Swap', 'Sell'],
      cartItemCount: 5,
      sideBarOpen:false,
    }
  },
  methods: {
    openSideBar(){
      this.sideBarOpen = true
    },
    closeSideBar(){
      this.sideBarOpen = false
    },
  },
  created() {
    
  },
}
</script>

<style>
@import '../styles/headerStyles.css';
</style>