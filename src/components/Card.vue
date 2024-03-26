<template>
  <div class="card">
    <div class="card-content">
      <div class="card-top flex">

        <div class="card-top-left">
          <div v-if="isOnSale" class="on-sale-indicator">
            <i class="fa-solid fa-circle on-sale-icon"></i>
            <span class="on-sale-text">ON SALE</span>
          </div>
          <div class="stock-indicator">
            <div v-if="inStock" class="in-stock">
              In stock
            </div>
            <div v-if="!inStock" class="out-of-stock">
              Out of stock
            </div>
          </div>
        </div>

        <div class="card-top-right">
          <div  v-if="true" class="amount-selector-container">
            <input v-model="amountToBuy" type="number" name="amount-selector" id="amount-selector" min="1" max="999" value=1>
            <div class="amount-buttons">
              <i class="fa-solid fa-caret-up amount-up" @click="checkAmount(1)"></i>
              <i class="fa-solid fa-caret-down amount-down" @click="checkAmount(2)"></i>
            </div>
          </div>
        </div>

      </div>

      <div class="card-img-middle">
        <img class="card-img" :src="image">
      </div>

      <div class="card-name-description-middle">
        <div class="description-top">
          <div class="description-name">
            {{ itemName }}
          </div>
          <div class="description-game-logo">
            <img class="game-logo" :src="itemGameImg">
            <div class="popup-game-name">
              {{ itemGame }}
            </div>
          </div>
        </div>
        <div class="description-prices">
          <div v-if="isOnSale" class="discount-price">
            {{ itemDiscountPrice }}
          </div>
          <div class="actual-price" :class="isOnSale ? 'on-sale-prices' : ''">
            {{ itemActualPrice }}
          </div>

        </div>
        <div class="description-text">
          {{ itemDescription }}
        </div>
      </div>

      <div class="card-bottom">
        <button class="details-button"> DETAILS </button>
        <button class="add-button">
          <div class="add-button-text">
            ADD
          </div>
          <div class="add-button-icon">
            <i class="fa-solid fa-cart-shopping"></i>
          </div>
        </button>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'Card',
  data() {
    return {
      amountToBuy:1,
      /* isOnSale:true,
      inStock:true,
      amountToBuy:1,

      image:"https://oldschool.runescape.wiki/images/thumb/3rd_age_druidic_cloak_detail.png/800px-3rd_age_druidic_cloak_detail.png?7bc73",

      itemName:"3rd age druidic cloak",
      itemGame:"OSRS",
      itemGameImg:"https://cdn2.steamgriddb.com/icon_thumb/6c8349cc7260ae62e3b1396831a8398f.png",

      itemDiscountPrice:'$200.00',
      itemActualPrice:'$350.75',

      itemDescription:"Lorem ipsum dolor sit amet, consectetur adipisicing elit.", */
    }
  },
  props: {
    isOnSale:{
      type: Boolean,
      default: false
    },
    inStock:{
      type: Boolean,
      default: true
    },
    image:{
      type: String,
      default: ''
    },
    itemName:{
      type: String,
      default: ''
    },
    itemGame:{
      type: String,
      default: 'OSRS'
    },
    itemGameImg:{
      type: String,
      default: 'https://cdn2.steamgriddb.com/icon_thumb/6c8349cc7260ae62e3b1396831a8398f.png'
    },
    itemDiscountPrice:{
      type: String,
      default: '$000.00'
    },
    itemActualPrice:{
      type: String,
      default: '$000.00'
    },
    itemDescription:{
      type: String,
      default: 'Lorem ipsum dolor sit amet'
    }

  },
  methods: {
    checkAmount(button){
      if(button == 1){
        if (this.amountToBuy < 999) {
          this.amountToBuy++
        }
      }
      if(button == 2){
        if (this.amountToBuy >= 2) {
          this.amountToBuy--
        }
      }
    }
  },
  mounted() {
    
  },
  watch:{
  }
}
</script>

<style>
@import '../styles/cardStyles.css';
.content{
  display: flex;
  flex-direction: column;
  align-items: center;
}
</style>