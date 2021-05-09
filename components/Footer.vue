<template>
  <footer>
    <img class="big-logo" :src="require('@/assets/big-logo.png')" alt="big-logo">
    <div class="social-block">
      <ul class="social-icons">
        <li class="icon">
          <a href="https://www.facebook.com/shambha.taiwan" target="_blank">
            <img :src="require('@/assets/social-icon1.png')" alt="social-icon">
          </a>
        </li>
        <li class="icon">
          <a href="https://www.instagram.com/shambha.bestcomb/" target="_blank">
            <img :src="require('@/assets/social-icon2.png')" alt="social-icon">
          </a>
        </li>
        <li class="icon">
          <a href="" target="_blank">
            <img :src="require('@/assets/social-icon3.png')" alt="social-icon">
          </a>
        </li>
      </ul>
      <p class="address">新北市深坑區深坑街18號 (深坑老街內)</p>
    </div>
    <div class="map-block">
      <div id="map" class="map"></div>
      <p class="copy-right">
        © 2021 香巴梳坊 All rights reserved.
      </p>
    </div>
  </footer>
</template>
<script>
const apiKey = 'AIzaSyBGCU5EPAn4upBIyygrhFKK1Ek8Vi-AVSE'
export default {
  head() {
    return {
      script: [
        {src: `https://maps.googleapis.com/maps/api/js?key=${apiKey}`}
      ]
    };
  },
  data() {
    return {
      map: null,
      lat: 25.0020224,
      lng: 121.6133893
    };
  },
  mounted() {
    this.initMap();
    this.setMarker();
  },
  methods: {
    initMap() {
      this.map = new google.maps.Map(document.getElementById("map"), {
        center: { lat: this.lat, lng: this.lng },
        zoom: 15,
        maxZoom: 20,
        minZoom: 3,
        streetViewControl: false,
        mapTypeControl: false
      });
    },
    setMarker() {
      const marker = new google.maps.Marker({
        position: { lat: this.lat, lng: this.lng },
        map: this.map
      });
    }
  }
}
</script>
<style lang="scss" scoped>
  footer {
    padding: 50px 150px 25px 150px;
    display: flex;
    align-items: center;
    justify-content: space-between;
    .big-logo {
      height: 150px;
    }
    .social-block {
      .social-icons {
        padding: 0;
        margin-bottom: 15px;
        .icon {
          display: inline-block;
          cursor: pointer;
          img {
            width: 30px;
            height: 30px;
          }
        }
        .icon + .icon {
          margin-left: 15px;
        }
      }
      .address {
        font-size: 16px;
        line-height: 1.56;
        letter-spacing: 0.45px;
        text-align: left;
        color: #320f0b;
      }
    }
    .map-block {
      .map {
        width: 300px;
        height: 150px;
        margin-bottom: 25px;
      }
      .copy-right {
        font-size: 16px;
        line-height: 1.56;
        letter-spacing: 0.45px;
        text-align: right;
        color: #320f0b;
      }
    }
    @media screen and (max-width: 992px){
      padding: 50px 50px 25px 50px;
    }
    @media screen and (max-width: 768px){
      padding: 50px 25px 25px 25px;
      flex-direction: column;
      .big-logo {
        margin-bottom: 50px;
      }
      .social-block {
        margin-bottom: 25px;
      }
      .map-block {
        .map {
          margin-bottom: 50px;
        }
      }
    }
  }
</style>
