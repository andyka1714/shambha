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
      <img class="arrow-down" :src="require('@/assets/arrow-down.svg')" alt="arrow-down">
    </div>
    <div class="why-wrap">
      <div class="why-block">
        <div class="content-block">
          <p class="content-title">為什麼選用牛角呢</p>
          <p class="content">
            除了食衣住行外，現代人對於生活質感也更傾向來自天然的呵護，牛角特有的溫潤手感，正符合我們對美好感受的想像；
            獨特的牛角肌理，也成為現代人自我品味的細節，藉由牛角梳一起享受生活中每個砰然心動的時刻吧！
          </p>
        </div>
        <img class="main-img" :src="require('@/assets/main-img.png')" alt="main-img">
      </div>
      <div class="why-block bg-pink margin-why-block">
        <div class="content-block padding-content">
          <p class="content-title">我們哪裡不一樣</p>
          <p class="content">
            市面上有種梳子，扁平齒細形狀一致，也稱之為牛角梳，這是為什麼呢？<br>
            原因是牛角在切割打磨的過程中會有許多牛角粉塵，這些粉塵經過搜集，高溫高壓朔型；簡單快速、成本低廉，但仍稱為牛角產品。<br>
            如此機械化的放棄牛角的美麗，我們覺得太可惜了，所以堅持每把梳子都要保留牛角最原始的美，我們沒辦法把齒開的這麼細，沒辦法每把都規格一致；但我們能給你牛角該有的樣子，使你的牛角梳獨一無二。
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
.bg-pink {
  background-color: #f3ece8;
}
.bg-white {
  background-color: #fff;
}
.container {
  background-color: #f5f5f5;
}
.main-img-block {
  height: 850px;
  background-size: cover;
  background-position: center right;
  display: flex;
  align-items: center;
  justify-content: center;
  padding: 20px;
  position: relative;
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
  .arrow-down {
    position: absolute;
    width: 60px;
    height: 60px;
    left: calc(50% - 30px);
    bottom: 50px;
    cursor: pointer;
  }
  @media screen and (max-width: 768px){
    height: 600px;
    .slogan-wrap {
      .slogan-block {
        padding: 20px 25px;
        .slogan {
          font-size: 20px;
        }
      }
    }
  }
  
  @media screen and (max-width: 450px){
    height: 350px;
    .slogan-wrap {
      padding: 16px;
      .slogan-block {
        padding: 14px 25px;
        .slogan {
          font-size: 14px;
          font-weight: 500;
          line-height: 1.46;
          letter-spacing: 0.88px;
          color: #3d1c18;
        }
      }
    }
    .arrow-down {
      position: absolute;
      width: 36px;
      height: 36px;
      left: calc(50% - 18px);
      bottom: 25px;
      cursor: pointer;
    }
  }
}
.why-wrap {
  padding: 0 150px;
  .why-block {
    height: 600px;
    display: flex;
    align-items: center;
    justify-content: space-between;
    .content-block {
      .content-title {
        font-size: 50px;
        line-height: 1.1;
        letter-spacing: 1.41px;
        color: #320f0b;
        font-weight: bold;
        margin-bottom: 10px;
      }
      .content {
        font-size: 26px;
        line-height: 1.54;
        letter-spacing: 1.43px;
        color: #320f0b;
      }
    }
    .content-block.padding-content {
      padding: 100px;
    }
    .main-img {
      width: 400px;
      height: 400px;
      margin-left: 150px;
    }
  }
  @media screen and (max-width: 1200px){
    padding: 0 100px;
    .why-block {
      .content-block {
        .content-title {
          font-size: 36px;
        }
        .content {
          font-size: 20px;
        }
      }
      .content-block.padding-content {
        padding: 80px;
      }
      .main-img {
        width: 300px;
        height: 300px;
        margin-left: 100px;
      }
    }
  }
  @media screen and (max-width: 992px){
    padding: 0 80px;
    .why-block {
      height: 480px;
      .content-block {
        .content-title {
          font-size: 26px;
        }
        .content {
          font-size: 18px;
        }
      }
      .content-block.padding-content {
        padding: 60px;
      }
      .main-img {
        width: 300px;
        height: 300px;
        margin-left: 60px;
      }
    }
  }
  @media screen and (max-width: 768px){
    padding: 0;
    .why-block {
      height: auto;
      flex-direction: column;
      .content-block {
        padding: 25px;
        .content-title {
          font-size: 26px;
        }
        .content {
          font-size: 18px;
        }
      }
      .content-block.padding-content {
        padding: 25px;
      }
      .main-img {
        width: 100%;
        height: auto;
        margin-left: 0;
      }
    }
    .why-block.margin-why-block {
      margin: 25px;
    }
  }
  
  @media screen and (max-width: 450px){
  }
}
</style>
