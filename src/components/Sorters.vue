<template>
  <div class="sorters">
    <div class="sorters-top">
      <h1 class="page-title">
        Condimentum consectetur
      </h1>
    </div>

    <div class="sorters-bottom">

      <div class="game-select">
        <img class="game-select-img" src="../assets/icons8-sword-50.png">
        <div class="game-select-text">Select a game</div>
        <i class="fa-solid fa-caret-down"></i>
        <i class="fa-solid fa-caret-up"></i>
      </div>

      <div class="item-search-bar-container">
        <div class="item-search-bar">

          <div class="item-search-icon">
            <i class="fa-solid fa-magnifying-glass"></i>
          </div>
          <div class="item-bar">
            <input type="text" name="item-bar" id="item-bar-search" placeholder="Search">
          </div>

        </div>
        <div class="side-sorters">
          <div class="price-sorter">
          <div class="price-left">
            <div class="price-icon">
              <i class="fa-solid fa-money-bills"></i>
            </div>
            <div class="price-sort">
              <div class="price-top-text">
                Price
              </div>
              <div class="price-bottom-text">
                All
              </div>
            </div>
          </div>
          <div class="price-arrows">
            <i class="fa-solid fa-caret-down"></i>
            <i class="fa-solid fa-caret-up"></i>
          </div>
        </div>

        <div class="type-sorter">
          <div class="type-left">
            <div class="type-icon">
              <i class="fa-solid fa-feather"></i>
            </div>
            <div class="type-sort">
              <div class="type-top-text">
                Item Type
              </div>
              <div class="type-bottom-text">
                All
              </div>
            </div>
          </div>
          <div class="type-arrows">
            <i class="fa-solid fa-caret-down"></i>
            <i class="fa-solid fa-caret-up"></i>
          </div>
        </div>
        </div>
        
      </div>

    </div>

  </div>
</template>

<script>

export default {
  name: 'Sorters',
}
</script>

<style>
@import '../styles/sortersStyles.css';
</style>