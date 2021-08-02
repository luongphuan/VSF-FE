<template>
  <div class="slider-block-wrapper">
    <swiper
      class="swiper gallery-top"
      :options="swiperOptionTop"
      ref="swiperTop"
    >
      <swiper-slide class="slide-1">
        <a
          href="https://cellphones.com.vn/tai-nghe-khong-day-huawei-freebuds-4.html?itm_sourcew=hp&amp;itm_mediumw=banner&amp;itm_campaignw=/tai-nghe-khong-day-huawei-freebuds-4.html&amp;itm_contentw=banner_690x300&amp;itm_termw=pre"
        >
          <img
            class="swiper-lazy swiper-lazy-loaded"
            alt="HUAWEI FREEBUDS 4 <BR> Đặt trước quà khủng"
            src="https://cdn.cellphones.com.vn/media/ltsoft/promotion/photo_2021-07-22_10-21-20.jpg"
          > </a>
      </swiper-slide>
      <swiper-slide class="slide-2">
        <a
          href="https://cellphones.com.vn/oppo-reno-6.html?itm_sourcew=hp&amp;itm_mediumw=banner&amp;itm_campaignw=/oppo-reno-6z.html&amp;itm_contentw=banner_690x300&amp;itm_termw=pre"
        >
          <img
            class="swiper-lazy swiper-lazy-loaded"
            alt="OPPO RENO6 SERIES <BR> Đặt trước nhận ưu đãi"
            src="https://cdn.cellphones.com.vn/media/ltsoft/promotion/reno-6-cps-690-300-max_1.png"
          >
        </a>
      </swiper-slide>
      <swiper-slide class="slide-3">
        <a
          href="https://cellphones.com.vn/iphone-11.html?itm_sourcew=hp&amp;itm_mediumw=sliding&amp;itm_campaignw=iphone_11&amp;itm_contentw=banner_690x300&amp;itm_termw=sale"
        >
          <img
            class="swiper-lazy swiper-lazy-loaded"
            alt="TẬU NGAY IPHONE 11 <BR> Siêu sale giảm khủng"
            src="https://cdn.cellphones.com.vn/media/ltsoft/promotion/bbb690x300_iPhone_11.png"
          >
        </a>
      </swiper-slide>
      <swiper-slide class="slide-4">
        <a
          href="https://cellphones.com.vn/xiaomi?itm_sourcew=hp&amp;itm_mediumw=banner&amp;itm_campaignw=/xiaomi&amp;itm_contentw=banner_690x300&amp;itm_termw=sale"
        >
          <img
            class="swiper-lazy swiper-lazy-loaded"
            alt="SMARTHOME XIAOMI <BR> Giảm đến 40%"
            src="https://cdn.cellphones.com.vn/media/ltsoft/promotion/cstm-690-300-max.png"
          >
        </a>
      </swiper-slide>
      <swiper-slide class="slide-5">
        <a
          href="https://cellphones.com.vn/tai-nghe-khong-day-jbl-live-pro-plus.html?itm_sourcew=hp&amp;itm_mediumw=banner&amp;itm_campaignw=/tai-nghe-khong-day-jbl-live-pro-plus.html&amp;itm_contentw=banner_690x300&amp;itm_termw=pre"
        >
          <img
            class="swiper-lazy swiper-lazy-loaded"
            alt="JBL LIVE PRO+ <BR> Đặt trước quà ngon"
            src="https://cdn.cellphones.com.vn/media/ltsoft/promotion/jl690-300-max.png"
          >
        </a>
      </swiper-slide>
      <div
        class="swiper-button-next swiper-button-white"
        slot="button-next"
      />
      <div
        class="swiper-button-prev swiper-button-white"
        slot="button-prev"
      />
    </swiper>
    <!-- swiper2 Thumbs -->
    <swiper
      class="swiper gallery-thumbs"
      :options="swiperOptionThumbs"
      ref="swiperThumbs"
    >
      <swiper-slide class="slide-1">
        GALAXY TAB S7 FE <br>
        Hotsale giảm sập sàn
      </swiper-slide>
      <swiper-slide class="slide-2">
        GALAXY TAB S7 FE <br>
        Hotsale giảm sập sàn
      </swiper-slide>
      <swiper-slide class="slide-3">
        TẬU NGAY IPHONE 11 <br> Siêu sale giảm khủng
      </swiper-slide>
      <swiper-slide class="slide-4">
        GALAXY TAB S7 FE <br>
        Hotsale giảm sập sàn
      </swiper-slide>
      <swiper-slide class="slide-5">
        GALAXY TAB S7 FE <br>
        Hotsale giảm sập sàn
      </swiper-slide>
    </swiper>
  </div>
</template>

<script>
import { Swiper, SwiperSlide, directive } from 'vue-awesome-swiper';
import 'swiper/css/swiper.css';

export default {
  name: 'Slider',
  components: {
    Swiper,
    SwiperSlide
  },
  //   directives: {
  //     swiper: directive,
  //   },
  data () {
    return {
      swiperOptionTop: {
        loop: true,
        loopedSlides: 5,
        spaceBetween: 10,
        // autoplay: {
        //   delay: 2500,
        //   disableOnInteraction: false,
        // },
        navigation: {
          nextEl: '.swiper-button-next',
          prevEl: '.swiper-button-prev'
        }
      },
      swiperOptionThumbs: {
        loop: true,
        // loopedSlides: 5,
        // centeredSlides: true,
        slidesPerView: 5,
        slidesPerGroup: 5,
        loopFillGroupWithBlank: true,
        slideToClickedSlide: true
      }
    };
  },
  computed: {
    swiperTop () {
      return this.$refs.swiperTop.$swiper;
    },
    swiperThumbs () {
      return this.$refs.swiperThumbs.$swiper;
    }
  },

  mounted () {
    this.swiperTop.controller.control = this.swiperThumbs;
    this.swiperThumbs.controller.control = this.swiperTop;
  }
};
</script>

<style lang="scss" scoped>
.slider-block-wrapper {
  height: 375.5px;
  width: 100%;
  .swiper-container {
    height: 100%;
    width: 100%;
  }
  .swiper {
    .swiper-slide {
      background-size: cover;
      background-position: center;
      overflow: hidden;
      a {
        width: 100%;
        height: 100%;
        img {
          width: calc(100% - 1px);
          height: 100%;
        }
      }
    }

    &.gallery-top {
        height: 304.34px;
        width: 100%;
    }
    &.gallery-thumbs {
    border-top: 1px solid #f4f4f4;
    background: #fff;
    position: unset;
    width: 100%;
    height: 72px;
    display: flex;
    justify-content: center;
    align-items: center;
    margin: 0;
    padding: 2px;
    border-radius: 0;
    background: #fff;
    font-size: 12px;
    line-height: 20px;
    text-align: center;
    color: #343a40;
    overflow: hidden;
    cursor: pointer;
    }
    &.gallery-thumbs .swiper-slide {
      width: calc(25% - 10px);
      height: 100%;
      opacity: 0.4;
      display: flex;
      justify-content: center;
      align-items: center;
    }
    &.gallery-thumbs .swiper-slide-active {
      opacity: 1;
          border-bottom: 2px solid #d70018!important;
    font-weight: 700;
    color: #343a40;
    }
  }
}
</style>
