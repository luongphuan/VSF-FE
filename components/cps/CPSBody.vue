<template>
  <div class="cps-body-wrapper mt-3">
    <div class="container">
      <div class="row">
        <div class="col-3 menu-col">
          <CategoryMenu :menu-items="menuItems" />
        </div>
        <div class="col-7">
          <Slider />
        </div>
        <div class="col-3 banner-col">
          <div class="row">
            <a
              href="https://cellphones.com.vn/samsung-galaxy-s21-plus.html?itm_sourcew=hp&amp;itm_mediumw=sliding&amp;itm_campaignw=samsung-galaxy-s21-ultra.html&amp;itm_contentw=banner_690x300&amp;itm_termw=trial"
            >
              <img
                height="115"
                src="https://cdn.cellphones.com.vn/media/ltsoft/promotion/sss21690-300-max.png"
              >
            </a>
          </div>
          <div class="row">
            <a
              href="https://cellphones.com.vn/mobile/apple/iphone-12-vna.html?itm_sourcew=hp&amp;itm_mediumw=sliding&amp;itm_campaignw=iphone-12.html&amp;itm_contentw=banner_690x300&amp;itm_termw=sale"
            >
              <img
                height="115"
                src="https://cdn.cellphones.com.vn/media/ltsoft/promotion/aiPhone_12_690x300_copy_3_.png"
              >
            </a>
          </div>
          <div class="row">
            <a
              href="https://cellphones.com.vn/laptop/asus/zenbook.html?itm_sourcew=hp&amp;itm_mediumw=sliding&amp;itm_campaignw=/laptop/asus/zenbook.html&amp;itm_contentw=banner_690x300&amp;itm_termw=sale"
            >
              <img
                height="115"
                src="https://cdn.cellphones.com.vn/media/ltsoft/promotion/a-640x278_Rightbanner_Textonly.png"
              >
            </a>
          </div>
        </div>
      </div>
      <div class="row mt-2 ml-0-mr-0">
        <a
          class="p-0"
          href="https://cellphones.com.vn/phu-kien-giam-gia?itm_sourcew=hp&amp;itm_mediumw=banner&amp;itm_campaignw=/phu-kien-giam-gia&amp;itm_contentw=banner_800x150&amp;itm_termw=sale"
          target="_blank"
        ><img
          src="https://cdn.cellphones.com.vn/media/wysiwyg/cv1200x75.png"
          width="1200"
        ></a>
      </div>
      <div class="row">
        <CategoryBlock />
      </div>
      <div class="row">
        <SliderBlock />
      </div>
      <div class="row">
        <AccessoriesBlock />
      </div>
    </div>
    <CPSFooter />
  </div>
</template>

<script>
import CategoryMenu from 'theme/components/custom/CategoryMenu';
import CategoryBlock from './CategoryBlock';
import AccessoriesBlock from './AccessoriesBlock';
import Slider from './Slider';
import SliderBlock from './SliderBlock';
import CPSFooter from './CPSFooter';

export default {
  name: 'CPSBody',
  components: {
    CategoryMenu,
    CategoryBlock,
    Slider,
    SliderBlock,
    CPSFooter,
    AccessoriesBlock
  },
  data () {
    return {
      isHoveredMenu: false,
      menuItems: [
        {
          icon: 'icon-cps-3',
          name: 'Điện thoại',
          subItems: [
            {
              name: 'Apple',
              subItems: [
                {
                  name: 'Iphone 12 Series'
                },
                {
                  name: 'Iphone 11 Series'
                }
              ]
            }
          ]
        },
        {
          icon: 'icon-cps-380',
          name: 'Laptop, PC, Màn hình',
          subItems: [
            {
              name: 'Apple',
              subItems: [
                {
                  name: 'Iphone 12 Series'
                },
                {
                  name: 'Iphone 11 Series'
                }
              ]
            }
          ]
        },
        {
          icon: 'icon-cps-4',
          name: 'Tablet',
          subItems: [
            {
              name: 'Apple',
              subItems: [
                {
                  name: 'Iphone 12 Series'
                },
                {
                  name: 'Iphone 11 Series'
                }
              ]
            }
          ]
        },
        {
          icon: 'icon-cps-220',
          name: 'Âm thanh',
          subItems: [
            {
              name: 'Apple',
              subItems: [
                {
                  name: 'Iphone 12 Series'
                },
                {
                  name: 'Iphone 11 Series'
                }
              ]
            }
          ]
        },
        {
          icon: 'icon-cps-610',
          name: 'Đồng hồ',
          subItems: [
            {
              name: 'Apple',
              subItems: [
                {
                  name: 'Iphone 12 Series'
                },
                {
                  name: 'Iphone 11 Series'
                }
              ]
            }
          ]
        },
        {
          icon: 'icon-cps-845',
          name: 'Nhà thông minh',
          subItems: [
            {
              name: 'Apple',
              subItems: [
                {
                  name: 'Iphone 12 Series'
                },
                {
                  name: 'Iphone 11 Series'
                }
              ]
            }
          ]
        },
        {
          icon: 'icon-cps-30',
          name: 'Phụ kiện',
          subItems: [
            {
              name: 'Apple',
              subItems: [
                {
                  name: 'Iphone 12 Series'
                },
                {
                  name: 'Iphone 11 Series'
                }
              ]
            }
          ]
        },
        {
          icon: 'icon-cps-tcdm',
          name: 'Thu cũ',
          subItems: [
            {
              name: 'Apple',
              subItems: [
                {
                  name: 'Iphone 12 Series'
                },
                {
                  name: 'Iphone 11 Series'
                }
              ]
            }
          ]
        },
        {
          icon: 'icon-cps-29',
          name: 'Hàng cũ',
          subItems: [
            {
              name: 'Apple',
              subItems: [
                {
                  name: 'Iphone 12 Series'
                },
                {
                  name: 'Iphone 11 Series'
                }
              ]
            }
          ]
        },
        {
          icon: 'icon-cps-123',
          name: 'Sim thẻ',
          subItems: [
            {
              name: 'Apple',
              subItems: [
                {
                  name: 'Iphone 12 Series'
                },
                {
                  name: 'Iphone 11 Series'
                }
              ]
            }
          ]
        },
        {
          icon: 'icon-cps-tech',
          name: 'Tin công nghệ'
        },
        {
          icon: 'icon-cps-promotion',
          name: 'Khuyến mại'
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
.cps-body-wrapper {
  .container {
    width: 1200px;
    min-width: 1200px;
    .menu-col {
      width: 220px;
      padding: 0;
    }
    .banner-col {
      width: calc(100% - (220px + 58.33333333%));
      .row:not(last-child) {
        margin-bottom: 15px;
      }
    }
  }
}
</style>
