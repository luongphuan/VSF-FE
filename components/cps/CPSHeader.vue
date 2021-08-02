<template>
  <div class="cps-header-wrapper">
    <div class="container">
      <div class="row">
        <div class="col-12 p-0">
          <div class="cps-header">
            <i class="cps-icon breadcrumb-icon" />
            <i class="cps-icon cps-logo" />
            <Select
              :options="['Hồ Chí Minh', 'Hà nội', 'Bình Dương', 'Hải Phòng']"
              :default="'Hồ Chí Minh'"
              class="select"
              label="Xem giá, tồn kho tại:"
            />
            <div class="search-container">
              <OSearch :class="{ 'desktop-only': !isSearchPanelVisible }" />
              <SfButton
                v-if="isSearchPanelVisible"
                class="sf-button--text form__action-button form__action-button--secondary mobile-only"
                @click="$store.commit('ui/setSearchpanel', false)"
              >
                {{ $t("Cancel") }}
              </SfButton>
            </div>
            <div class="action-block">
              <div class="contact-block">
                <i class="cps-icon phone-icon" />
                <div>
                  <p>Gọi mua hàng</p>
                  <strong>1800.2097</strong>
                </div>
              </div>
              <div class="location-block">
                <i class="cps-icon location-icon" />
                <p>Tìm cửa hàng</p>
              </div>
              <div class="cart-block">
                <i class="cps-icon cart-icon" />
                <p>Giỏ hàng</p>
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import { SfButton } from '@storefront-ui/vue';
import OSearch from 'theme/components/organisms/o-search';
import Select from 'theme/components/custom/Select';
import { mapState, mapGetters } from 'vuex';

export default {
  name: 'CPSHeader',
  components: {
    SfButton,
    OSearch,
    Select
  },
  data () {
    return {
      isHoveredMenu: false,
      options: []
    };
  },
  computed: {
    ...mapState({
      isSearchPanelVisible: state => state.ui.searchpanel
    }),
    ...mapState('ui', ['isMobileMenu']),
    ...mapGetters('category', ['getCategories', 'getCurrentCategory']),
    ...mapGetters('user', ['isLoggedIn'])
  },
  methods: {

  },
  watch: {
    async isMobileMenu (status) {
      if (this.isMobileMenu) {
        // we can't add this style to body because sfui also add/remove overflow to body and there may be conflict
        document.documentElement.style.overflow = 'hidden';
      } else {
        document.documentElement.style.overflow = '';
      }
    }
  }
};
</script>

<style lang="scss">
.cps-header-wrapper {
  background-color: #d70018;
  .container {
    width: 1200px;
    min-width: 1200px;
  }
  .action-block {
    width: 424px;
    display: flex;
    justify-content: space-between;
    align-items: center;
    margin-left: 15px;
    color: white;
    align-items: center;
    i {
      margin-right: 5px;
    }
    p {
      margin: 0;
      font-size: 14px;
    }
    .contact-block {
      display: flex;
      align-items: center;
      i {
        margin-right: 5px;
      }
      div {
        display: flex;
        flex-direction: column;
      }
    }
    .location-block,
    .cart-block {
      display: flex;
      align-items: center;
    }
  }
  .cps-header {
    height: 64px;
    display: flex;
    align-items: center;
  }
  .cps-logo {
    width: 167px;
    height: 30px;
    background-size: 450px;
    background-position: -54px -65.5px;
  }
  .phone-icon {
    width: 28px;
    height: 28px;
    background-size: 500px;
    background-position: -140px -262px;
  }
  .breadcrumb-icon {
    width: 35px;
    height: 30px;
    background-size: 500px;
    background-position: -233px -260.5px;
  }
  .location-icon {
    width: 28px;
    height: 28px;
    background-size: 500px;
    background-position: -93px -262px;
  }
  .cart-icon {
    width: 28px;
    height: 28px;
    background-size: 470px;
    background-position: -174.5px -245.5px;
  }
  .sf-search-bar {
    width: 415px;
    padding: 3px;
    input {
      background-color: white;
      border: none;
      border-radius: 4px;
      margin-left: 15px;
      height: 38px;
      &::placeholder {
        padding-left: 5px;
      }
    }
    span {
      top: 6px;
      right: 6px;
    }
  }
  .sf-search-bar input:focus-visible {
    outline: none;
    padding-left: 10px;
  }
}
</style>
