<template>
  <header>
    <img @click="scrollToItem('main')" :src="require('@/assets/logo.png')" alt="logo" class="logo">
    <div class="navs">
      <a @click="scrollToItem('why')">選用牛角</a>
      <a @click="scrollToItem('different')">哪裡不一樣</a>
      <a @click="scrollToItem('products')">熱銷商品</a>
      <a @click="scrollToItem('instruction')">使用方式</a>
      <a href="https://shopee.tw/tzumon2020" class="button-link" target="_blank">
        前往賣場
        <img :src="require('@/assets/white-arrow-right.png')" alt="arrow">
      </a>
    </div>
    <img v-if="!showMobileLink" :src="require('@/assets/menu.png')" @click="toggleShowMobileLin" alt="menu" class="menu-icon">
    <img v-else :src="require('@/assets/menu-cancel.png')" @click="toggleShowMobileLin" alt="menu-cancel" class="menu-icon">
    <div class="mobile-navs" :class="{ 'hide-link': !showMobileLink }">
      <div class="white-border-wrap">
        <a @click="scrollToItem('why')">選用牛角</a>
        <a @click="scrollToItem('different')">哪裡不一樣</a>
        <a @click="scrollToItem('products')">熱銷商品</a>
        <a @click="scrollToItem('instruction')">使用方式</a>
        <a href="https://shopee.tw/tzumon2020" target="_blank">前往賣場</a>
      </div>
    </div>
  </header>
</template>
<script>
export default {
  data() {
    return {
      showMobileLink: false
    }
  },
  methods: {
    toggleShowMobileLin() {
      this.showMobileLink = !this.showMobileLink
    },
    scrollToItem(item) {
      this.showMobileLink = false
      this.$emit('scrollToItem', item)
    }
  }
}
</script>
<style lang="scss" scoped>
  header {
    width: 100%;
    height: 50px;
    background-color: #f3ece8;
    padding: 7px 25px;
    display: flex;
    align-items: center;
    justify-content: space-between;
    position: relative;
    .logo {
      height: 30px;
      width: auto;
      cursor: pointer;
    }
  }
  .navs {
    a {
      font-size: 16px;
      font-weight: 500;
      color: #320f0b;
      text-decoration: none;
      margin-right: 25px;
      cursor: pointer;
    }
    a.button-link {
      padding: 6px 16px;
      border-radius: 25px;
      background-color: #320f0b;
      color: #fff;
      margin-right: 0;
      img {
        width: 12px;
        height: 12px;
      }
    }
  }
  .mobile-navs {
    width: 100%;
    height: auto;
    display: none;
    background-color: #f3ece8;
    padding: 25px;
    position: absolute;
    top: 50px;
    left: 0;
    transition: all .2s linear;
    transform: scaleY(1);
    transform-origin: center top;
    z-index: 999;
    .white-border-wrap {
      border: solid 1px #ffffff;
      text-align: center;
      padding: 15px;
      display: flex;
      flex-direction: column;
      a {
        font-size: 16px;
        font-weight: 500;
        color: #320f0b;
        text-decoration: none;
      }
      a + a {
        margin-top: 16px;
      }
    }
  }
  .menu-icon {
    display: none;
    width: 30px;
    height: 20px;
    cursor: pointer;
  }
  .hide-link {
    transform: scaleY(0);
    padding: 0 25px;
    overflow: hidden;
  }
  @media only screen and (max-width: 768px) {
    .navs {
      display: none;
    }
    .mobile-navs {
      display: block;
    }
    .menu-icon {
     display: block; 
    }
  }
</style>
