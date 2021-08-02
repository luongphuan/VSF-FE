<template>
  <div
    class="custom-select"
    :tabindex="tabindex"
    @blur="open = false"
    @click="open = !open"
  >
    <div class="select-label" v-if="label">
      {{ label }}
    </div>
    <div class="selected" :class="{ open: open }">
      {{ selected }}
    </div>
    <div class="items" :class="{ selectHide: !open }">
      <div
        v-for="(option, i) of options"
        :key="i"
        @click="
          selected = option;
          open = false;
          $emit('input', option);
        "
      >
        <i class="bi bi-geo-alt-fill" />
        {{ option }}
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'Select',
  props: {
    options: {
      type: Array,
      required: true
    },
    label: {
      type: String,
      required: false,
      default: null
    },
    default: {
      type: String,
      required: false,
      default: null
    },
    tabindex: {
      type: Number,
      required: false,
      default: 0
    }
  },
  data () {
    return {
      selected: this.default
        ? this.default
        : this.options.length > 0
          ? this.options[0]
          : null,
      open: false
    };
  },
  mounted () {
    this.$emit('input', this.selected);
  }
};
</script>

<style lang="scss">
.custom-select {
  display: flex;
  flex-direction: column;
  justify-content: center;
  position: relative;
  text-align: left;
  outline: none;
  height: 47px;
  width: auto;
  min-width: 110px;
  max-width: 150px;
  height: 38px;
  padding: 0 5px;
  border-radius: 4px;
  background: rgba(255, 255, 255, 0.3);
  color: #fff;
  cursor: pointer;
}

.custom-select .selected {
  border-radius: 6px;
  color: #fff;
  cursor: pointer;
  user-select: none;
  font-size: 12px;
}

.custom-select .selected:after {
  position: absolute;
  content: "";
  top: 26px;
  right: 1em;
  width: 0;
  height: 0;
  border: 5px solid transparent;
  border-color: #fff transparent transparent transparent;
}

.custom-select .items {
  color: black;
  overflow: hidden;
  position: absolute;
  background-color: white;
  top: 40px;
  left: 0;
  right: 0;
  z-index: 1;
  min-width: 160px;
  border-radius: 4px;
  div {
    display: flex;
    align-items: center;
    font-size: 15px;
    padding: 3px 20px;
    font-weight: 400;
    line-height: 1.42857143;
  }
  i {
    display: inline-block;
    font-size: 12px;
    text-rendering: auto;
    -webkit-font-smoothing: antialiased;
    margin-right: 5px;
  }
}

.custom-select .items div {
  padding-left: 1em;
  cursor: pointer;
  user-select: none;
}

.custom-select .items div:hover {
  background-color: #f4f4f4;
}
.select-label {
  font-size: 10px;
}

.selectHide {
  display: none;
}
</style>
