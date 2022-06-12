<template>
  <div :class="{ 'app-search': true, '-focus': focused }">
    <search-icon class="icon" />
    <input class="search" @focus="onFocusSearch" @blur="onBlurSearch" />
  </div>
</template>

<script>
import SearchIcon from '@/assets/image/icon/search.svg?inline'

export default {
  components: {
    SearchIcon,
  },

  data() {
    return {
      focused: false,
    }
  },

  methods: {
    onFocusSearch() {
      this.focused = true
    },

    onBlurSearch() {
      this.focused = false
    },
  },
}
</script>

<style lang="scss">
.app-search {
  position: relative;

  &.-focus {
    > .icon {
      color: #000;
    }

    > .search {
      background-color: #fff;
    }
  }

  > .icon {
    width: 20px;
    height: 20px;
    position: absolute;
    color: #fff;
    top: 6px;
    left: 6px;
  }

  > .search {
    height: 32px;
    outline: none;
    font-size: 14px;
    background-color: rgba(255, 255, 255, 0.2);
    border: 1px solid rgba(255, 255, 255, 0.25);
    padding-left: 30px;
    padding-right: 8px;
    border-radius: 4px;
    width: 250px;
  }
}
</style>
