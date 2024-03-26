<template>
  <div class="card-display">
    <div class="showing-pages-main-sort">
      <div class="showing-pages">
        Showing {{cardItems.length}} - from 165
      </div>
      <div class="main-sort">
        <div class="sort-icon">
          <i class="fa-solid fa-sliders"></i>
        </div>
        <div class="main-sorter">
          <div class="main-sorter-top">
            Sort By
          </div>
          <div class="main-sorter-bottom">
            Featured
          </div>
        </div>
        <div class="select-icon">
          <i class="fa-solid fa-caret-down"></i>
          <i class="fa-solid fa-caret-up"></i>
        </div>
      </div>
    </div>
    <div class="cards-displayed">
      <template v-for="card in cardItems" :key="(card.itemName,index)">
          <Card 
            :isOnSale="card.isOnSale" 
            :inStock="card.inStock" 
            :image="card.image" 
            :itemName="card.itemName"
            :itemGame="card.itemGame"
            :itemGameImg="card.itemGameImg"
            :itemDiscountPrice="card.itemDiscountPrice"
            :itemActualPrice="card.itemActualPrice"
            :itemDescription="card.itemDescription"
          />
          <div :class="index%2 == 0 ? 'break': ''"></div>
      </template>
    </div>
    <div class="pagination">
      <div class="previous-button page-button">
        <div class="previous-icon">
          <i class="fa-solid fa-angle-left"></i>
        </div>
      </div>
      <div class="item-pages">
        <template v-for="n in 6" :key="n">
          <div class="page-button" :class="n == 1 ? 'page-active' : n == 5 ? 'ellipsis-page' : ''">
            <span v-if="n < 5">{{ n }}</span>
            <span v-if="n == 5"> ... </span>
            <span v-if="n == 6"> 11 </span>
          </div>
        </template>
      </div>
      <div class="next-button page-button">
        <div class="next-icon">
          <i class="fa-solid fa-angle-right"></i>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import Card from './Card.vue';
export default {
  name: 'CardDisplay',
  components:{
    Card,
  },
  data() {
    return {
      cardItems:[
        {
          isOnSale:true,
          inStock:true,

          image:"https://oldschool.runescape.wiki/images/thumb/Eldritch_orb_detail.png/800px-Eldritch_orb_detail.png?7d608",

          itemName:"Eldritch Orb",
          itemGame:"OSRS",
          itemGameImg:"https://cdn2.steamgriddb.com/icon_thumb/6c8349cc7260ae62e3b1396831a8398f.png",

          itemDiscountPrice:'$105.23',
          itemActualPrice:'$146.59',

          itemDescription:"Lorem ipsum dolor sit amet, consectetur adipisicing elit.",
        },

        {
          isOnSale:true,
          inStock:true,

          image:"https://oldschool.runescape.wiki/images/thumb/3rd_age_druidic_cloak_detail.png/800px-3rd_age_druidic_cloak_detail.png?7bc73",

          itemName:"3rd age druidic cloak",
          itemGame:"OSRS",
          itemGameImg:"https://cdn2.steamgriddb.com/icon_thumb/6c8349cc7260ae62e3b1396831a8398f.png",

          itemDiscountPrice:'$200.00',
          itemActualPrice:'$350.75',

          itemDescription:"Lorem ipsum dolor sit amet, consectetur adipisicing elit.",
        },

        {
          isOnSale:false,
          inStock:true,

          image:"https://oldschool.runescape.wiki/images/thumb/Magus_ring_detail.png/150px-Magus_ring_detail.png?7d63e",

          itemName:"Magus Ring",
          itemGame:"OSRS",
          itemGameImg:"https://cdn2.steamgriddb.com/icon_thumb/6c8349cc7260ae62e3b1396831a8398f.png",

          itemDiscountPrice:'$200.00',
          itemActualPrice:'$15.21',

          itemDescription:"Lorem ipsum dolor sit amet, consectetur adipisicing elit.",
        },

        {
          isOnSale:false,
          inStock:false,

          image:"https://oldschool.runescape.wiki/images/thumb/Imbued_heart_detail.png/800px-Imbued_heart_detail.png?be01a",

          itemName:"Imbued Heart",
          itemGame:"OSRS",
          itemGameImg:"https://cdn2.steamgriddb.com/icon_thumb/6c8349cc7260ae62e3b1396831a8398f.png",

          itemDiscountPrice:'$15.00',
          itemActualPrice:'$20.15',

          itemDescription:"Lorem ipsum dolor sit amet, consectetur adipisicing elit.",
        },

        {
          isOnSale:true,
          inStock:true,

          image:"https://oldschool.runescape.wiki/images/thumb/Harmonised_orb_detail.png/800px-Harmonised_orb_detail.png?83d4d",

          itemName:"Harmonised Orb",
          itemGame:"OSRS",
          itemGameImg:"https://cdn2.steamgriddb.com/icon_thumb/6c8349cc7260ae62e3b1396831a8398f.png",

          itemDiscountPrice:'$75.10',
          itemActualPrice:'$83.21',

          itemDescription:"Lorem ipsum dolor sit amet, consectetur adipisicing elit.",
        },

        {
          isOnSale:true,
          inStock:true,

          image:"https://oldschool.runescape.wiki/images/thumb/Volatile_orb_detail.png/800px-Volatile_orb_detail.png?4cd7c",

          itemName:"Volatile Orb",
          itemGame:"OSRS",
          itemGameImg:"https://cdn2.steamgriddb.com/icon_thumb/6c8349cc7260ae62e3b1396831a8398f.png",

          itemDiscountPrice:'$20.87',
          itemActualPrice:'$22.96',

          itemDescription:"Lorem ipsum dolor sit amet, consectetur adipisicing elit.",
        },

        {
          isOnSale:false,
          inStock:false,

          image:"https://oldschool.runescape.wiki/images/thumb/Kodai_wand_detail.png/1200px-Kodai_wand_detail.png?1ad2b",

          itemName:"Kodai Wand",
          itemGame:"OSRS",
          itemGameImg:"https://cdn2.steamgriddb.com/icon_thumb/6c8349cc7260ae62e3b1396831a8398f.png",

          itemDiscountPrice:'$200.00',
          itemActualPrice:'$35.57',

          itemDescription:"Lorem ipsum dolor sit amet, consectetur adipisicing elit.",
        },

        {
          isOnSale:false,
          inStock:true,

          image:"https://oldschool.runescape.wiki/images/thumb/Dragon_full_helm_detail.png/1200px-Dragon_full_helm_detail.png?6edab",

          itemName:"Dragon Full Helm",
          itemGame:"OSRS",
          itemGameImg:"https://cdn2.steamgriddb.com/icon_thumb/6c8349cc7260ae62e3b1396831a8398f.png",

          itemDiscountPrice:'$200.00',
          itemActualPrice:'$16.54.75',

          itemDescription:"Lorem ipsum dolor sit amet, consectetur adipisicing elit.",
        },

        {
          isOnSale:true,
          inStock:true,

          image:"https://oldschool.runescape.wiki/images/thumb/Scythe_of_vitur_%28uncharged%29_detail.png/1200px-Scythe_of_vitur_%28uncharged%29_detail.png?939b9",

          itemName:"Scythe of Vitur",
          itemGame:"OSRS",
          itemGameImg:"https://cdn2.steamgriddb.com/icon_thumb/6c8349cc7260ae62e3b1396831a8398f.png",

          itemDiscountPrice:'$234.53',
          itemActualPrice:'$257.98',

          itemDescription:"Lorem ipsum dolor sit amet, consectetur adipisicing elit.",
        },

        {
          isOnSale:false,
          inStock:true,

          image:"https://oldschool.runescape.wiki/images/thumb/Amulet_of_eternal_glory_detail.png/800px-Amulet_of_eternal_glory_detail.png?34ecf",

          itemName:"Amulet of Eternal Glory",
          itemGame:"OSRS",
          itemGameImg:"https://cdn2.steamgriddb.com/icon_thumb/6c8349cc7260ae62e3b1396831a8398f.png",

          itemDiscountPrice:'$200.00',
          itemActualPrice:'$15.31',

          itemDescription:"Lorem ipsum dolor sit amet, consectetur adipisicing elit.",
        },

        {
          isOnSale:true,
          inStock:true,

          image:"https://oldschool.runescape.wiki/images/thumb/Ancestral_hat_detail.png/800px-Ancestral_hat_detail.png?b438f",

          itemName:"Ancestral Hat",
          itemGame:"OSRS",
          itemGameImg:"https://cdn2.steamgriddb.com/icon_thumb/6c8349cc7260ae62e3b1396831a8398f.png",

          itemDiscountPrice:'$10.00',
          itemActualPrice:'$11.54.75',

          itemDescription:"Lorem ipsum dolor sit amet, consectetur adipisicing elit.",
        },

        {
          isOnSale:false,
          inStock:true,

          image:"https://oldschool.runescape.wiki/images/thumb/Tormented_bracelet_detail.png/800px-Tormented_bracelet_detail.png?ef9b1",

          itemName:"Tormented Bracelet",
          itemGame:"OSRS",
          itemGameImg:"https://cdn2.steamgriddb.com/icon_thumb/6c8349cc7260ae62e3b1396831a8398f.png",

          itemDiscountPrice:'$200.00',
          itemActualPrice:'$2.39',

          itemDescription:"Lorem ipsum dolor sit amet, consectetur adipisicing elit.",
        },

        {
          isOnSale:false,
          inStock:false,

          image:"https://oldschool.runescape.wiki/images/thumb/Armadyl_helmet_detail.png/800px-Armadyl_helmet_detail.png?8793d",

          itemName:"Armadyl Helmet",
          itemGame:"OSRS",
          itemGameImg:"https://cdn2.steamgriddb.com/icon_thumb/6c8349cc7260ae62e3b1396831a8398f.png",

          itemDiscountPrice:'$200.00',
          itemActualPrice:'$2.12',

          itemDescription:"Lorem ipsum dolor sit amet, consectetur adipisicing elit.",
        },

        {
          isOnSale:false,
          inStock:true,

          image:"https://oldschool.runescape.wiki/images/thumb/Sanguinesti_staff_%28uncharged%29_detail.png/640px-Sanguinesti_staff_%28uncharged%29_detail.png?6c90d",

          itemName:"Sanguinesti Staff",
          itemGame:"OSRS",
          itemGameImg:"https://cdn2.steamgriddb.com/icon_thumb/6c8349cc7260ae62e3b1396831a8398f.png",

          itemDiscountPrice:'$18.52',
          itemActualPrice:'$20.37',

          itemDescription:"Lorem ipsum dolor sit amet, consectetur adipisicing elit.",
        },

        {
          isOnSale:true,
          inStock:true,

          image:"https://oldschool.runescape.wiki/images/thumb/Nightmare_staff_detail.png/1200px-Nightmare_staff_detail.png?51fcd",

          itemName:"Nightmare Staff",
          itemGame:"OSRS",
          itemGameImg:"https://cdn2.steamgriddb.com/icon_thumb/6c8349cc7260ae62e3b1396831a8398f.png",

          itemDiscountPrice:'$9.70',
          itemActualPrice:'$10.67',

          itemDescription:"Lorem ipsum dolor sit amet, consectetur adipisicing elit.",
        },

      ]
    }
  },
}
</script>

<style>
@import '../styles/cardDisplayStyles.css';
</style>