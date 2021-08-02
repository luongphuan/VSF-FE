<template>
  <div class="category-block-wrapper p-0">
    <div class="block-header">
      <div class="left-block-header">
        <a
          href="https://cellphones.com.vn/mobile.html"
          class="text-reset text-decoration-none"
        >
          <strong>Điện thoại nổi bật nhất</strong>
        </a>
      </div>
      <div class="right-block-header">
        <a href="https://cellphones.com.vn/mobile.html">Xem tất cả</a>
      </div>
    </div>
    <div class="block-items">
      <swiper class="swiper" :options="swiperBlockSetting">
        <swiper-slide v-for="product in products" :key="product.id">
          <div class="product-item">
            <ProductItem :product="product" />
          </div>
        </swiper-slide>
        <div class="swiper-pagination" slot="pagination" />
        <div class="swiper-button-prev" slot="button-prev" />
        <div class="swiper-button-next" slot="button-next" />
      </swiper>
    </div>
  </div>
</template>

<script>
import ProductItem from './ProductItem';
import { Swiper, SwiperSlide, directive } from 'vue-awesome-swiper';
import 'swiper/css/swiper.css';

export default {
  name: 'SliderBlock',
  components: {
    ProductItem,
    Swiper,
    SwiperSlide
  },
  data () {
    return {
      isHoveredMenu: false,
      swiperBlockSetting: {
        slidesPerView: 5,
        slidesPerGroup: 5,
        loop: true,
        loopFillGroupWithBlank: true,
        navigation: {
          nextEl: '.swiper-button-next',
          prevEl: '.swiper-button-prev'
        }
      },
      products: [
        {
          id: 1,
          url: 'https://cellphones.com.vn/iphone-11.html',
          image:
            'https://cdn.cellphones.com.vn/media/catalog/product/cache/7/small_image/220x175/9df78eab33525d08d6e5fb8d27136e95/l/a/layer_20.jpg',
          sale: '18%',
          name: 'iPhone 11 I Chính hãng VN/A',
          specialPrice: 14700000,
          oldPrice: 18000000,
          promotion:
            'Giảm thêm 500.000đ khi mua kèm Apple Watch Series 6 và 2 km khác',
          rating: 5,
          numberOfRating: 46
        },
        {
          id: 2,
          url: 'https://cellphones.com.vn/iphone-11.html',
          image:
            'https://cdn.cellphones.com.vn/media/catalog/product/cache/7/small_image/220x175/9df78eab33525d08d6e5fb8d27136e95/l/a/layer_20.jpg',
          sale: '18%',
          name: 'iPhone 11 I Chính hãng VN/A',
          specialPrice: 14700000,
          oldPrice: 18000000,
          promotion:
            'Giảm thêm 500.000đ khi mua kèm Apple Watch Series 6 và 2 km khác',
          rating: 5,
          numberOfRating: 46
        },
        {
          id: 3,
          url: 'https://cellphones.com.vn/iphone-11.html',
          image:
            'https://cdn.cellphones.com.vn/media/catalog/product/cache/7/small_image/220x175/9df78eab33525d08d6e5fb8d27136e95/l/a/layer_20.jpg',
          sale: '18%',
          name: 'iPhone 11 I Chính hãng VN/A',
          specialPrice: 14700000,
          oldPrice: 18000000,
          promotion:
            'Giảm thêm 500.000đ khi mua kèm Apple Watch Series 6 và 2 km khác',
          rating: 5,
          numberOfRating: 46
        },
        {
          id: 4,
          url: 'https://cellphones.com.vn/iphone-11.html',
          image:
            'https://cdn.cellphones.com.vn/media/catalog/product/cache/7/small_image/220x175/9df78eab33525d08d6e5fb8d27136e95/l/a/layer_20.jpg',
          sale: '18%',
          name: 'iPhone 11 I Chính hãng VN/A',
          specialPrice: 14700000,
          oldPrice: 18000000,
          promotion:
            'Giảm thêm 500.000đ khi mua kèm Apple Watch Series 6 và 2 km khác',
          rating: 5,
          numberOfRating: 46
        },
        {
          id: 5,
          url: 'https://cellphones.com.vn/iphone-11.html',
          image:
            'https://cdn.cellphones.com.vn/media/catalog/product/cache/7/small_image/220x175/9df78eab33525d08d6e5fb8d27136e95/l/a/layer_20.jpg',
          sale: '18%',
          name: 'iPhone 11 I Chính hãng VN/A',
          specialPrice: 14700000,
          oldPrice: 18000000,
          promotion:
            'Giảm thêm 500.000đ khi mua kèm Apple Watch Series 6 và 2 km khác',
          rating: 5,
          numberOfRating: 46
        },
        {
          id: 6,
          url: 'https://cellphones.com.vn/iphone-11.html',
          image:
            'https://cdn.cellphones.com.vn/media/catalog/product/cache/7/small_image/220x175/9df78eab33525d08d6e5fb8d27136e95/l/a/layer_20.jpg',
          sale: '18%',
          name: 'iPhone 11 I Chính hãng VN/A',
          specialPrice: 14700000,
          oldPrice: 18000000,
          promotion:
            'Giảm thêm 500.000đ khi mua kèm Apple Watch Series 6 và 2 km khác',
          rating: 5,
          numberOfRating: 46
        },
        {
          id: 7,
          url: 'https://cellphones.com.vn/iphone-11.html',
          image:
            'https://cdn.cellphones.com.vn/media/catalog/product/cache/7/small_image/220x175/9df78eab33525d08d6e5fb8d27136e95/l/a/layer_20.jpg',
          sale: '18%',
          name: 'iPhone 11 I Chính hãng VN/A',
          specialPrice: 14700000,
          oldPrice: 18000000,
          promotion:
            'Giảm thêm 500.000đ khi mua kèm Apple Watch Series 6 và 2 km khác',
          rating: 5,
          numberOfRating: 46
        },
        {
          id: 8,
          url: 'https://cellphones.com.vn/iphone-11.html',
          image:
            'https://cdn.cellphones.com.vn/media/catalog/product/cache/7/small_image/220x175/9df78eab33525d08d6e5fb8d27136e95/l/a/layer_20.jpg',
          sale: '18%',
          name: 'iPhone 11 I Chính hãng VN/A',
          specialPrice: 14700000,
          oldPrice: 18000000,
          promotion:
            'Giảm thêm 500.000đ khi mua kèm Apple Watch Series 6 và 2 km khác',
          rating: 5,
          numberOfRating: 46
        },
        {
          id: 9,
          url: 'https://cellphones.com.vn/iphone-11.html',
          image:
            'https://cdn.cellphones.com.vn/media/catalog/product/cache/7/small_image/220x175/9df78eab33525d08d6e5fb8d27136e95/l/a/layer_20.jpg',
          sale: '18%',
          name: 'iPhone 11 I Chính hãng VN/A',
          specialPrice: 14700000,
          oldPrice: 18000000,
          promotion:
            'Giảm thêm 500.000đ khi mua kèm Apple Watch Series 6 và 2 km khác',
          rating: 5,
          numberOfRating: 46
        },
        {
          id: 10,
          url: 'https://cellphones.com.vn/iphone-11.html',
          image:
            'https://cdn.cellphones.com.vn/media/catalog/product/cache/7/small_image/220x175/9df78eab33525d08d6e5fb8d27136e95/l/a/layer_20.jpg',
          sale: '18%',
          name: 'iPhone 11 I Chính hãng VN/A',
          specialPrice: 14700000,
          oldPrice: 18000000,
          promotion:
            'Giảm thêm 500.000đ khi mua kèm Apple Watch Series 6 và 2 km khác',
          rating: 5,
          numberOfRating: 46
        }
      ]
    };
  },
  computed: {},
  methods: {},
  watch: {}
};
</script>

<style lang="scss" scoped>
.category-block-wrapper {
  width: 100%;
  .block-header {
    display: flex;
    justify-content: space-between;
    align-items: center;
    width: 100%;
    padding: 10px;
    background-color: #f8f8f8;
    .left-block-header {
      font-size: 16px;
      line-height: 1.5;
      text-transform: uppercase;
      color: #222;
    }
    .right-block-header {
      display: flex;
      align-items: center;
      a {
        padding: 5px 15px;
        background: #fff;
        border: 0;
        border-radius: 15px;
        box-shadow: 0 0 1px rgba(0, 0, 0, 0.08);
        font-size: 12px;
        line-height: 1.5;
        text-decoration: none;
        color: #666;
        cursor: pointer;
        -webkit-transition: 0.3s ease-out;
        -moz-transition: 0.3s ease-out;
        -ms-transition: 0.3s ease-out;
        -o-transition: 0.3s ease-out;
        transition: 0.3s ease-out;
        &:hover {
          background: #eee;
        }
      }
    }
  }
  .block-items {
    display: flex;
    width: 100%;
    flex-wrap: wrap;
    .product-item {
      width: 100%;
    }
    .swiper-slide{
      width: 20%;
    }
  }
}
</style>
