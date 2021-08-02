<template>
  <div class="product-item-wrapper">
    <div class="product-image">
      <a href="https://cellphones.com.vn/iphone-11.html">
        <img
          src="https://cdn.cellphones.com.vn/media/catalog/product/cache/7/small_image/220x175/9df78eab33525d08d6e5fb8d27136e95/l/a/layer_20.jpg"
        >
        <div class="product__box-sticker">
          <p class="sticker-percent">{{ product.sale }}</p>
          <i class="cps-icon icon-sale" />
        </div>
      </a>
    </div>
    <div class="product-name">
      <h3>{{ product.name }}</h3>
    </div>
    <div class="product-price">
      <p class="special-price">
        {{ formatPrice(product.specialPrice) }}
      </p>
      <p class="old-price">
        {{ formatPrice(product.oldPrice) }}&nbsp;₫
      </p>
    </div>
    <div class="product-promotion">
      <p>
        {{ product.promotion }}
      </p>
    </div>
    <div class="product-rating">
      <i class="bi bi-star-fill" />
      <i class="bi bi-star-fill" />
      <i class="bi bi-star-fill" />
      <i class="bi bi-star-fill" />
      <i class="bi bi-star-fill" />
      &nbsp;{{ product.numberOfRating }}&nbsp;đánh giá
    </div>
    <div class="product-buttons">
      <a href="https://cellphones.com.vn/iphone-12-pro-max.html" class="btn-buy">Mua ngay</a>
      <a
        href="https://cellphones.com.vn/so-sanh/iphone-12-pro-max"
        class="btn-compare"
      >So sánh</a>
    </div>
  </div>
</template>

<script>
export default {
  name: 'ProductItem',
  components: {},
  props: {
    product: {
      type: Object,
      required: true,
      default: () => {}
    }
  },
  data () {
    return {
      isHoveredMenu: false,
      options: []
    };
  },
  methods: {
    formatPrice (price) {
      return price.toString().replace(/\B(?=(\d{3})+(?!\d))/g, ',');
    }
  }
};
</script>

<style lang="scss" scoped>
.product-item-wrapper {
  position: relative;
  height: 100%;
  padding: 10px;
  background-color: white;
  &:hover {
    z-index: 3;
    &::before {
      content: "";
      position: absolute;
      top: 0;
      right: 0;
      bottom: 0;
      left: 0;
      height: calc(100% + 40px);
      border: solid 1px #ddd;
      border-radius: 2px;
      box-shadow: 0 3px 6px 0 rgba(0, 0, 0, 0.16);
      background-color: #fff;
      -webkit-transition: 0.3s;
      -moz-transition: 0.3s;
      -o-transition: 0.3s;
      transition: 0.3s;
    }
    .product-image img {
      -webkit-transform: scale(1.04);
      transform: scale(1.04);
    }
    .product-buttons {
      visibility: visible;
      opacity: 1;
    }
  }
  .product-image {
    width: 100%;
    height: 180px;
    display: flex;
    align-items: center;
    margin: 15px 0;
    position: relative;
    -webkit-transition: 0.3s;
    -moz-transition: 0.3s;
    -o-transition: 0.3s;
    transition: 0.3s;
    a {
      height: 100%;
      display: flex;
      align-items: center;
    }
  }
  .sticker-percent {
    width: 39px;
    height: 35px;
    display: flex;
    justify-content: center;
    align-items: center;
    padding: 0 0 5px !important;
    margin: 0 !important;
    background-image: url(https://cdn.cellphones.com.vn/media/icon/icons_menubar-11.svg);
    background-repeat: no-repeat;
    background-size: 900px;
    background-position: -594px -255px;
    font-size: 12px;
    font-weight: 700;
    color: #fff;
    position: absolute;
    top: -25px;
    left: 0;
    overflow: hidden;
  }
  .icon-sale {
    margin: 0 !important;
    position: absolute;
    left: 0;
    bottom: 0;
    width: 40px;
    height: 50px;
    background-position: -248px -122px;
    background-size: 480px !important;
    &::after {
      content: "HOT SALE";
      height: 50px;
      display: flex;
      justify-content: center;
      align-items: center;
      padding: 20px 0 0;
      font-size: 8px;
      font-weight: 700;
      line-height: 1.2;
      font-style: italic;
      color: #fff;
      text-align: center;
    }
  }
  .product-name {
    position: relative;
    width: 100%;
    h3 {
      margin-bottom: 0;
      font-size: 14px;
      font-weight: 700;
      line-height: 1.4em;
      color: #222;
      text-align: left;
      display: -webkit-box;
      -webkit-line-clamp: 3;
      -webkit-box-orient: vertical;
      overflow: hidden;
    }
  }
  .product-price {
    position: relative;
    width: 100%;
    p {
      display: inline-block;
    }
    .special-price {
      font-size: 14px;
      font-weight: 700;
      color: #d70018;
    }
    .old-price {
      font-size: 12px;
      color: #716b6b;
      text-decoration: line-through;
      margin: 0 !important;
    }
  }
  .product-promotion {
    position: relative;
    margin-bottom: 10px;
    padding: 5px !important;
    border-radius: 2px;
    background-color: #f8f8f8;
    p {
      margin-bottom: 0;
      font-size: 12px;
      line-height: 1.4;
      color: #444;
      text-align: left;
      display: -webkit-box;
      -webkit-line-clamp: 3;
      -webkit-box-orient: vertical;
      overflow: hidden;
    }
  }
  .product-rating {
    position: relative;
    font-size: 12px;
    line-height: 1.2;
    i {
      color: orange;
    }
  }
  .product-buttons {
    visibility: hidden;
    display: flex;
    padding: 10px;
    position: absolute;
    left: 0;
    bottom: -40px;
    opacity: 0;
    -webkit-transition: 0.3s;
    -moz-transition: 0.3s;
    -o-transition: 0.3s;
    transition: 0.3s;
    width: 100%;
    a {
      width: calc(100% - 10px);
      height: 30px;
      display: flex;
      justify-content: center;
      align-items: center;
      border-radius: 2px;
      font-size: 12px;
      font-weight: 700;
      text-align: center;
      color: #fff;
      text-decoration: none;
    }
    .btn-buy {
      background-image: linear-gradient(to bottom, #f52f32, #d70018 50%);
      margin-right: 10px;
    }
    .btn-compare {
      background-image: linear-gradient(
        to bottom,
        rgba(108, 117, 125, 0.8),
        #6c757d 50%
      );
    }
  }
}
</style>
