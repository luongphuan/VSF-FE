<template>
  <ul class="category-menu-wrapper">
    <li v-for="(item, index) in menuItems" :key="index" class="menu-item">
      <a href="https://cellphones.com.vn/mobile.html">
        <i :class="['cps-icon '+ item.icon]" />
        <span>{{ item.name }}</span>
        <i v-if="item.subItems" class="bi bi-caret-right" />
        <ul v-if="item.subItems" class="menu-item-child">
          <li
            v-for="(sub, index) in item.subItems"
            :key="index"
            class="menu-item"
          >
            <a href="https://cellphones.com.vn/sim-3g-4g-nghe-goi/the-cao.html">
              <span>{{ sub.name }}</span>
              <i v-if="item.subItems" class="bi bi-caret-right" />
              <ul v-if="sub.subItems" class="sub-item">
                <li
                  v-for="(sub2, index) in sub.subItems"
                  :key="index"
                  class="menu-item"
                >
                  <a
                    href="https://cellphones.com.vn/sim-3g-4g-nghe-goi/the-cao.html"
                  >
                    <span>{{ sub2.name }}</span>
                  </a>
                </li>
              </ul>
            </a>
          </li>
          <li class="menu-item">
            <a
              href="https://cellphones.com.vn/sim-3g-4g-nghe-goi/dich-vu-sim.html"
            >
              <span>Dịch vụ sim</span>
            </a>
          </li>
        </ul>
      </a>
    </li>
  </ul>
</template>

<script>
export default {
  name: 'CategoryMenu',
  props: {
    menuItems: {
      type: Array,
      required: true,
      default: () => []
    }
  },
  methods: {
    getIconClass (icon) {
      return 'cps-icon ' + icon;
    }
  }
};
</script>

<style lang="scss">
.category-menu-wrapper {
  position: relative;
  width: 100%;
  height: 375.5px;
  margin: 0;
  padding: 0;
  list-style: none;
  border-radius: 2px;
  background: #fff;
  box-shadow: 0 0.125rem 0.25rem rgba(0, 0, 0, 0.075) !important;
  .menu-item {
    a {
      min-height: 31.3px;
      display: flex;
      align-items: center;
      padding: 0 10px;
      background: 0 0;
      font-size: 12px;
      font-weight: 700;
      text-decoration: none !important;
      color: #343a40;
      transition: 0.3s;
    }
    &:hover {
      background-color: #f8f8f8;
      .menu-item-child {
        visibility: visible;
        opacity: 1;
        &:hover .sub-item {
          visibility: visible;
          opacity: 1;
        }
      }
    }
    .menu-item-child,
    .sub-item {
      padding-left: 0;
      background-color: white;
      width: 220px;
      height: auto;
      min-height: 375px;
      visibility: hidden;
      box-shadow: 0 0.5rem 1rem rgba(0, 0, 0, 0.15) !important;
      position: absolute;
      top: 0;
      right: -218px;
      z-index: 100;
      opacity: 0;
      list-style: none;
      border-radius: 2px;
    }
    .bi-caret-right {
      margin-left: auto;
    }
  }
}
.cps-icon {
  width: 25px;
  height: 25px;
  margin-right: 5px;
}
.icon-cps-3 {
  background-size: 300px !important;
  background-position: 5px -182px;
}
.icon-cps-380 {
  background-size: 280px !important;
  background-position: -21px -168px;
}
.icon-cps-4 {
  background-size: 280px !important;
  background-position: -47px -168px;
}
.icon-cps-220 {
  background-size: 300px !important;
  background-position: -80px -182px;
}
.icon-cps-610 {
  background-size: 300px !important;
  background-position: -107px -182px;
}
.icon-cps-845 {
  background-size: 300px !important;
  background-position: -135px -182px;
}
.icon-cps-30 {
  background-size: 350px !important;
  background-position: -192px -214px;
}
.icon-cps-tcdm {
  background-size: 300px !important;
  background-position: -192px -182px;
}
.icon-cps-29 {
  background-size: 280px !important;
  background-position: -204px -167px;
}
.icon-cps-123 {
  background-size: 300px !important;
  background-position: -247px -182px;
}
.icon-cps-tech {
  background-size: 280px !important;
  background-position: -256px -168px;
}
.icon-cps-promotion {
  background-size: 300px !important;
  background-position: -23px -210px;
}
</style>
