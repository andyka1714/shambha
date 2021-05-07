<template>
  <div class="container">
    <Header></Header>
    <div class="main-img-block" :style="{ backgroundImage: `url(${require('@/assets/pci.png')})`}">
      <div class="slogan-wrap">
        <div class="slogan-block">
          <p class="slogan">
            在深坑老街有一間小小的牛角梳店，裡面充滿了許多讓生活明亮而美好的神奇小寶物。<br>
            來吧！歡迎來到香巴梳坊！ 
          </p>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import Header from '~/components/Header.vue'

export default {
  components: {
    Header
  }
}
</script>

<style lang="scss" scoped>
.main-img-block {
  height: 850px;
  background-size: cover;
  background-position: center right;
  display: flex;
  align-items: center;
  justify-content: center;
  padding: 20px;
  .slogan-wrap {
    max-width: 800px;
    background-color: rgba(243, 236, 232, 0.8);
    padding: 25px;
    .slogan-block {
      padding: 38px 50px;
      border: solid 2px #320f0b;
      .slogan {
        font-size: 28px;
        font-weight: 500;
        line-height: 1.46;
        letter-spacing: 0.88px;
        color: #3d1c18;
      }
    }
  }
  @media screen and (max-width: 768px){
    .slogan-wrap {
      .slogan-block {
        padding: 20px 25px;
      }
    }
  }
  
  @media screen and (max-width: 450px){
    height: 500px;
    .slogan-wrap {
      .slogan-block {
        padding: 20px 25px;
        .slogan {
          font-size: 18px;
          font-weight: 500;
          line-height: 1.46;
          letter-spacing: 0.88px;
          color: #3d1c18;
        }
      }
    }
  }
}
</style>
