<template>
  <div class="footer">
    <div class="footer-top showbig">

      <div class="payments-icons">
        <template v-for="method in payments" :key="method.name">
          <div class="payment-icon">
            <img :class="method.name+'-icon'" :src="method.icon" alt="" width="50px" height="30px">
          </div>
        </template>
        <div class="more-text">
          and 50+ more
        </div>
      </div>

    </div>
    <div class="footer-middle">
      <div class="socials-icons">
        <template v-for="social in socials" :key="social.name">
          <div class="social-icon">
            <img :class="social.name+'-icon'" :src="social.icon" alt="" width="30px" height="30px">
          </div>
        </template>
      </div>
    </div>
    <div class="footer-bottom">
      <div class="footer-bottom-info">
        <div class="cg-logo-mail">
          <img class="logo-mail" src="https://chicksgold.com/logo/chicks-logo-large.svg">
          <div class="support-mail">
            support@chicksgold.com
          </div>
        </div>
        <div class="info-bits">
          <template v-for="bit in infoPages" :key="bit.parent">
            <div :class="transfomrToClassName(bit.parent)" class="info-bit"  @mouseenter="openChildContainer($event.target)">
              <div class="bit-parent" :class="transfomrToClassName(bit.parent)">
                {{ bit.parent }}
                <div class="bit-children-container hidden" :id="transfomrToClassName(bit.parent)+'-children'" @mouseleave="closeChildContainer($event.target)">
                  <template v-for="child in bit.children" :key="child">
                    <div class="bit-children">
                      {{ child }}
                    </div>
                  </template>
                </div>
              </div>
            </div>
          </template>
        </div>
        <div class="trust-rating">
          <div class="trust-big show-big">
            <template v-for="n in 5" :key="n">
              <img class="big-trust-star" src="https://thumbs.dreamstime.com/b/white-star-green-background-vector-illustration-100370770.jpg">
            </template>
            <div class="big-trust-text">
              Trustpilot Reviews
            </div>
          </div>
          <div class="trust-small dont-show-big">
            <img class="small-trust-star" src="https://png.pngtree.com/png-vector/20230124/ourmid/pngtree-five-star-rating-with-gold-color-and-3d-style-png-image_6565096.png" alt="">
            <div class="small-trust-text">
              Trustpilot Reviews
            </div>
          </div>
        </div>
      </div>
    </div>
    <div class="copyright-bottom">
      © 2017 - 2020 ChicksGold.com. All Rights Reserved.
    </div>
  </div>
</template>

<script>
export default {
  name: 'Footer',
  data() {
    return {
      payments:[
        {
          name:'visa',
          icon: "https://cdn4.iconfinder.com/data/icons/flat-brand-logo-2/512/visa-512.png"
        },
        {
          name:'mastercard',
          icon: "https://static-00.iconduck.com/assets.00/mastercard-icon-2048x1225-3kb6axel.png"
        },
        {
          name:'american-express',
          icon: "https://cdn.icon-icons.com/icons2/1487/PNG/512/8365-american-express_102492.png"
        },
        {
          name:'skrill',
          icon: "https://upload.wikimedia.org/wikipedia/commons/thumb/1/1b/Skrill_logo.svg/2560px-Skrill_logo.svg.png"
        },
        {
          name:'bitcoin',
          icon: "https://cdn.icon-icons.com/icons2/1487/PNG/512/8369-bitcoin_102502.png"
        },
      ],
      socials:[
        {
          name:"facebook",
          icon:"https://upload.wikimedia.org/wikipedia/commons/thumb/b/b8/2021_Facebook_icon.svg/2048px-2021_Facebook_icon.svg.png"
        },
        {
          name:"instagram",
          icon:"https://png.pngtree.com/png-clipart/20230401/original/pngtree-three-dimensional-instagram-icon-png-image_9015419.png"
        },
        {
          name:"twitter",
          icon:"https://cdn3.iconfinder.com/data/icons/basicolor-reading-writing/24/077_twitter-512.png"
        },
        {
          name:"discord",
          icon:"https://uxwing.com/wp-content/themes/uxwing/download/brands-and-social-media/discord-round-color-icon.png"
        },
      ],
      infoPages:[
        {
          parent:'Chicks Gold',
          children:['Games','About Us','Blog', 'Sitemap']
        },
        {
          parent:'Support',
          children:['Contact Us', 'FAQ']
        },
        {
          parent:'Legal',
          children:['Privacy Policy','Terms of Service','Copyright Policy']
        },
      ]
    }
  },
  methods: {
    transfomrToClassName(name){
      let className = name.toLowerCase()
      if(className.includes(' ')){
        className = className.split(' ')
        className = className.join('-')
      }
      return className
    },
    openChildContainer(target){
      let targetChildContainer = document.getElementById(`${target.classList[0]}-children`)
      targetChildContainer.classList.remove('show-close')  
      targetChildContainer.classList.remove('hidden')
      targetChildContainer.classList.add('show-open')
    },
    closeChildContainer(target){
      let targetChildContainer = document.getElementById(`${target.id}`)
      targetChildContainer.classList.remove('show-open')
      targetChildContainer.classList.add('show-close')
      setTimeout(() => {
        targetChildContainer.classList.add('hidden')
      }, 200);
    },
  },
}
</script>

<style>
@import '../styles/footerStyles.css';
</style>