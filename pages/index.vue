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
    <div class="fill-title-wrap">
      <div class="fill-title-block">
        <h2 class="title">- 熱銷商品 -</h2>
      </div>
    </div>
    <div class="product-list">
      <div class="product"
        :class="{ reverse: (index % 2 === 1) }" 
        v-for="(product, index) in productList">
        <div class="product-img" :style="{ backgroundImage: `url(${product.img})`}"></div>
        <div class="product-content-block bg-pink">
          <p class="title">{{ product.title }}</p>
          <p class="content">{{ product.content }}</p>
          <p v-if="product.attentionContent" class="attention">{{ product.attentionContent }}</p>
          <a :href="product.link" class="link" target="_blank">立即購買></a>
        </div>
      </div>
    </div>
    <div class="fill-title-wrap">
      <div class="fill-title-block">
        <h2 class="title">- 使用方法 -</h2>
      </div>
    </div>
    <div class="instruction-list">
      <div 
        class="instruction-wrap"
        v-for="(instruction, index) in instructionList"
        :class="{ reverse: (index % 2 === 1) }" >
        <div class="instruction-title-warp bg-pink" :class="{ left: (index % 2 === 0), right: (index % 2 === 1) }">
          <img :src="instruction.titleImg" alt="instruction-title">
        </div>
        <div class="instruction">
          <div class="instruction-content-block bg-white">
            <p class="content">{{ instruction.content }}</p>
          </div>
          <img class="instruction-img" :src="instruction.img" alt="instruction-img">
        </div>
      </div>
    </div>
    <div class="recruit-block bg-pink">
      <img :src="require('@/assets/recruit-title.png')" alt="recruit-title">
      <a href="https://shopee.tw/tzumon2020" class="link" target="_blank">
        前往賣場
        <img :src="require('@/assets/arrow-shopping.png')" alt="arrow-shopping">
      </a>
    </div>
    <div class="white-block"></div>
    <Footer class="bg-pink"></Footer>
  </div>
</template>

<script>
import Header from '~/components/Header.vue'
import Footer from '~/components/Footer.vue'

export default {
  components: {
    Header,
    Footer
  },
  data() {
    return {
      productList: [
        {
          title: '天然牛角按摩髮梳',
          attentionContent: '細齒-著重頭髮梳理，建議直髮使用\n寬齒-不破壞捲髮線條，建議捲髮使用',
          content: '為忙碌的生活淨化思緒，享受微微酥麻的頭皮感受；利用牛角不易產生靜電的特性，讓你細心照顧的秀髮維持輕盈自然；每把梳子都是來自天然的獨一無二。\n\n',
          link: 'https://shopee.tw/%E3%80%94%E9%A6%99%E5%B7%B4%E6%A2%B3%E5%9D%8A%E3%80%95%E5%A4%A9%E7%84%B6%E7%89%9B%E8%A7%92%E6%8C%89%E6%91%A9%E9%AB%AE%E6%A2%B3-i.59235586.7559858832',
          img: require('@/assets/product1.png')
        },
        {
          title: '舒緩刮痧板',
          attentionContent: null,
          content: '以舒適的姿勢手握刮痧板，服貼每寸肌膚，搭配精油或乳液進行肩頸或身體大面積刮痧，兩尖端處亦可用來按摩下巴輪廓和眉間穴道。\n多款形狀，讓您挑選最適合自己的商品。',
          link: 'https://shopee.tw/%E3%80%94%E9%A6%99%E5%B7%B4%E6%A2%B3%E5%9D%8A%E3%80%95%E8%88%92%E9%AB%94%E6%84%9B%E5%BF%83%E5%88%AE%E7%97%A7%E6%9D%BF-i.59235586.4861309321',
          img: require('@/assets/product2.png')
        },
        {
          title: '細緻眼周按摩棒',
          attentionContent: null,
          content: '扁平端搭配眼霜或乳液輕柔按摩眼周肌膚，圓端則稍微帶點力道的按壓臉部穴道。\n體積精緻輕巧，適用任何部位較細緻的按摩刮痧。',
          link: 'https://shopee.tw/%E3%80%94%E9%A6%99%E5%B7%B4%E6%A2%B3%E5%9D%8A%E3%80%95%E7%B4%B0%E7%B7%BB%E7%9C%BC%E5%91%A8%E6%8C%89%E6%91%A9%E6%A3%92-i.59235586.6860040607',
          img: require('@/assets/product3.png')
        },
        {
          title: '多功能魚型刮痧板',
          attentionContent: null,
          content: '刮痧板界的十項全能王!\n手握魚尾桶，基礎的肩頸刮痧，凹陷處服貼身體線條，鋸齒處撥筋按摩，扁平狀適用於拍痧，魚尾貼合手指、下巴輪廓；居家旅遊必備單品。',
          link: 'https://shopee.tw/%E3%80%94%E9%A6%99%E5%B7%B4%E6%A2%B3%E5%9D%8A%E3%80%95%E5%A4%9A%E5%8A%9F%E8%83%BD%E9%AD%9A%E5%BD%A2%E5%88%AE%E7%97%A7%E6%9D%BF-i.59235586.8935479362',
          img: require('@/assets/product4.png')
        },
        {
          title: '穴道按摩錐',
          attentionContent: null,
          content: '一隻牛角只有一個的尖端直接切割打磨。\n尖端精準按壓穴道，圓頭端充滿力道的穴道經絡揉壓。完美扎實手感怎麼捨得放下它。',
          link: 'https://shopee.tw/%E3%80%94%E9%A6%99%E5%B7%B4%E6%A2%B3%E5%9D%8A%E3%80%95%E7%89%9B%E8%A7%92%E7%A9%B4%E9%81%93%E6%8C%89%E6%91%A9%E9%8C%90-i.59235586.8635392163',
          img: require('@/assets/product5.png')
        },
        {
          title: '白牛角印鑑章',
          attentionContent: null,
          content: '最常見的個人章尺寸為六分，邊長(直徑)1.8公分，為六六大順之意。\n方章和圓章的挑選取決於用途，傳統習俗中圓章代表財源滾滾，生意投資滾滾來；方章則象徵四平八穩，購屋置產絕對不能少。',
          link: 'https://shopee.tw/%E3%80%94%E9%A6%99%E5%B7%B4%E6%A2%B3%E5%9D%8A%E3%80%95%E7%99%BD%E7%89%9B%E8%A7%92%E5%8D%B0%E9%91%91%E7%AB%A0-i.59235586.3964281838',
          img: require('@/assets/product6.png')
        }
      ],
      instructionList: [
        {
          titleImg: require('@/assets/instruction-title1.png'),
          content: '別忘了一定要梳到頭皮 ！從髮際各處往中間梳，就像想綁個從容的小馬尾，記得試試由後頸往前梳，享受徹底照顧自己的過程，讓你的頭皮恢復輕盈，蓬鬆有活力的頭髮永遠賞心悅目。',
          img: require('@/assets/instruction1.png')
        },
        {
          titleImg: require('@/assets/instruction-title2.png'),
          content: '記得小時候每當酷暑，祖母的舒緩妙招嗎 ？由肩頸延伸至背部，由上往下、單一方向刮痧，無論是青草膏還是草本按摩精油，承襲來自古老的呵護。',
          img: require('@/assets/instruction2.png')
        },
        {
          titleImg: require('@/assets/instruction-title3.png'),
          content: '還有什麼比緊實的輪廓更重要，按壓眼周、臉部穴道，順著肌膚紋理輕輕刮，讓緊繃了整天的眉間放鬆，回到渾然天成的美，和你珍貴乳霜一起完成優雅的下顎線條。',
          img: require('@/assets/instruction3.png')
        },
        {
          titleImg: require('@/assets/instruction-title4.png'),
          content: '絕對不會忽略任何一寸肌膚，沖洗完身體搭配最愛的乳液或精油，由腳踝往上慢慢推刮，放鬆肌肉線條，一天的疲憊在嗅覺和觸覺都被療癒，看不到的地方更要溫柔對待。',
          img: require('@/assets/instruction4.png')
        }
      ]
    }
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
          font-size: 22px;
        }
        .content {
          font-size: 16px;
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
}
.fill-title-wrap {
  margin: 100px 150px;
  .fill-title-block {
    background-color: #c3ada2;
    padding: 10px;
    .title {
      text-align: center;
      font-size: 50px;
      font-weight: bold;
      letter-spacing: 1.41px;
      color: #ffffff;
      border: solid 2px #ffffff;
      padding: 29px;
    }
  }
  @media screen and (max-width: 1200px){
    margin: 80px 100px;
  }
  @media screen and (max-width: 992px){
    margin: 60px 80px;
    .fill-title-block {
      .title {
        font-size: 36px;
        padding: 20px;
      }
    }
  }
  @media screen and (max-width: 768px){
    margin: 25px 0;
    .fill-title-block {
      .title {
        font-size: 22px;
        padding: 14px;
      }
    }
  }
}
.product-list {
  .product {
    height: 600px;
    display: flex;
    align-items: center;
    justify-content: center;
    .product-img, .product-content-block {
      width: 50%;
      height: 600px;
    }
    .product-img {
      background-size: cover;
      background-repeat: no-repeat;
      background-position: center;
    }
    .product-content-block {
      padding: 0 100px 0 50px;
      display: flex;
      align-items: flex-start;
      justify-content: center;
      flex-direction: column;
      .title {
        font-size: 50px;
        font-weight: bold;
        letter-spacing: 1.41px;
        color: #320f0b;
        margin-bottom: 10px;
      }
      .content, .attention {
        font-size: 26px;
        line-height: 1.54;
        letter-spacing: 1.43px;
        color: #320f0b;
        white-space: pre-wrap;
      }
      .attention {
        font-weight: 500;
      }
      .link {
        font-size: 26px;
        font-weight: 500;
        letter-spacing: 1.43px;
        color: #ae061b;
        margin-top: 25px;
      }
    }
  }
  .product + .product {
    margin-top: 100px;
  }
  .reverse {
    flex-direction: row-reverse;
    .product-content-block {
      padding: 0 50px 0 100px;
    }
  }
  @media screen and (max-width: 1200px){
    .product {
      .product-content-block {
        padding: 0 80px 0 40px;
        .title {
          font-size: 36px;
        }
        .content, .attention {
          font-size: 20px;
        }
        .link {
          font-size: 20px;
        }
      }
    }
    .reverse {
      .product-content-block {
        padding: 0 40px 0 80px;
      }
    }
  }
  @media screen and (max-width: 992px){
    .product {
      height: 480px;
      .product-img, .product-content-block {
        height: 480px;
      }
      .product-content-block {
        .title {
          font-size: 26px;
        }
        .content, .attention {
          font-size: 18px;
        }
        .link {
          font-size: 18px;
        }
      }
    }
  }
  @media screen and (max-width: 768px){
    .product {
      height: auto;
      flex-direction: column-reverse;
      .product-img, .product-content-block {
        width: 100%;
      }
      .product-img {
        height: 350px;
      }
      .product-content-block {
        padding: 25px 25px 50px 25px;
        height: auto;
        .title {
          font-size: 22px;
        }
        .content, .attention {
          font-size: 16px;
        }
        .link {
          font-size: 16px;
        }
      }
    }
    .product + .product {
      margin-top: 25px;
    }
    .reverse {
      .product-content-block {
        padding: 30px;
      }
    }
  }
}
.instruction-list {
  .instruction-wrap {
    position: relative;
    padding: 75px 150px 100px 150px;
    .instruction-title-warp {
      position: absolute;
      top: 0;
      padding: 25px;
      width: 500px;
      text-align: center;
      img {
        height: 100px;
      }
    }
    .left {
      left: 0;
    }
    .right {
      right: 0;
    }
    .instruction {
      height: 425px;
      display: flex;
      align-items: center;
      justify-content: center;
      .instruction-img, .instruction-content-block {
        height: 425px;
      }
      .instruction-img {
        width: 425px;
        background-size: cover;
        background-repeat: no-repeat;
        background-position: center;
      }
      .instruction-content-block {
        width: calc(100% - 425px);
        padding: 0 50px 0 100px;
        display: flex;
        align-items: flex-start;
        justify-content: center;
        flex-direction: column;
        .content {
          font-size: 26px;
          line-height: 1.54;
          letter-spacing: 1.43px;
          color: #320f0b;
          white-space: pre-wrap;
        }
      }
    }
  }
  .reverse {
    .instruction {
      flex-direction: row-reverse;
      .instruction-content-block {
        padding: 0 100px 0 50px;
      }
    }
  }
  @media screen and (max-width: 1200px){
    .instruction-wrap {
      .instruction-title-warp {
        padding: 20px;
        width: 400px;
        img {
          height: 80px;
        }
      }
      .instruction {
        .instruction-content-block {
          padding: 0 40px 0 80px;
          .content {
            font-size: 20px;
          }
        }
      }
    }
    .reverse {
      .instruction {
        flex-direction: row-reverse;
        .instruction-content-block {
          padding: 0 80px 0 40px;
        }
      }
    }
  }
  @media screen and (max-width: 992px){
    .instruction-wrap {
      padding: 50px;
      .instruction-title-warp {
        padding: 20px;
        width: 400px;
        img {
          height: 80px;
        }
      }
      .instruction {
        height: 350px;
        .instruction-img, .instruction-content-block {
          height: 350px;
        }
        .instruction-img {
          width: 350px;
        }
        .instruction-content-block {
          width: calc(100% - 350px);
          .content {
            font-size: 18px;
          }
        }
      }
    }
  }
  @media screen and (max-width: 768px){
    .instruction-wrap {
      padding: 25px;
      .instruction-title-warp {
        padding: 12px;
        width: 250px;
        img {
          height: 50px;
        }
      }
      .instruction {
        height: auto;
        flex-direction: column;
        .instruction-img, .instruction-content-block {
          width: 100%;
        }
        .instruction-img {
          width: 100%;
          height: auto;
        }
        .instruction-content-block {
          padding: 0;
          height: auto;
          .content {
            letter-spacing: 0.88px;
            padding: 62px 25px 25px 25px;
            font-size: 16px;
          }
        }
      }
    }
  }
}
.recruit-block {
  padding: 100px 200px;
  display: flex;
  align-items: center;
  justify-content: space-between;
  img {
    height: 100px;
    width: auto;
  }
  a {
    font-size: 50px;
    font-weight: bold;
    letter-spacing: 1.41px;
    color: #320f0b;
    display: flex;
    align-items: center;
    text-decoration: none;
    img {
      width: 38px;
      height: 38px;
      margin: 25px;
    }
  }
  @media screen and (max-width: 1200px){
    padding: 80px 160px;
    img {
      height: 80px;
    }
    a {
      font-size: 40px;
      img {
        width: 30px;
        height: 30px;
        margin: 20px;
      }
    }
  }
  @media screen and (max-width: 992px){
    padding: 50px;
    img {
      height: 60px;
    }
    a {
      font-size: 30px;
      img {
        width: 24px;
        height: 24px;
        margin: 15px;
      }
    }
  }
  @media screen and (max-width: 768px){
    padding: 25px;
    flex-direction: column;
    img {
      height: 40px;
      margin-bottom: 20px;
    }
    a {
      font-size: 22px;
      img {
        width: 16px;
        height: 16px;
        margin: 10px;
      }
    }
  }
}
.white-block {
  height: 110px;
}
</style>
