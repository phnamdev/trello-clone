<template>
  <div :class="['app-workspace', { '-collapsed': !isExpand }]">
    <div class="firstletter">
      {{ firstLetterUpperCase }}
    </div>
    <div class="name">
      <span class="text">
        {{ name }}
      </span>
    </div>
    <div class="navigation" @click.stop="toggleExpand">
      <chevron-left-icon v-if="isExpand" />
      <chevron-right-icon v-else />
    </div>
  </div>
</template>

<script>
import ChevronLeftIcon from '@/assets/image/icon/chevron-left.svg'
import ChevronRightIcon from '@/assets/image/icon/chevron-right.svg'

export default {
  name: 'AppWorkspace',

  components: {
    ChevronLeftIcon,
    ChevronRightIcon,
  },

  props: {
    name: {
      type: String,
      default: '',
    },

    isExpand: Boolean,
  },

  emits: ['change-expand'],

  computed: {
    firstLetterUpperCase() {
      return this.name?.[0].toUpperCase()
    },
  },

  methods: {
    toggleExpand() {
      this.$emit('update:isExpand', !this.isExpand)
    },
  },
}
</script>

<style lang="scss">
.app-workspace {
  padding: 14px 12px;
  display: flex;
  align-items: center;
  border-bottom: 1px solid hsla(0, 0%, 100%, 0.16);

  > .firstletter {
    width: 32px;
    height: 32px;
    color: #fff;
    text-align: center;
    line-height: 32px;
    font-size: 20px;
    font-weight: bold;

    background: linear-gradient(#006644, #00875a);
  }

  > .name {
    flex: 1;
    margin-left: 8px;
    margin-right: 4px;

    > .text {
      display: -webkit-box;
      -webkit-line-clamp: 2;
      -webkit-box-orient: vertical;
      overflow: hidden;
      text-overflow: ellipsis;
      color: #fff;
      line-height: 20px;
      font-size: 14px;
      font-weight: 600;
    }
  }

  > .navigation {
    cursor: pointer;
    width: 32px;
    height: 32px;
    color: #fff;
    cursor: pointer;
    display: flex;
    justify-content: center;
    align-items: center;

    &:hover {
      background-color: rgba(255, 255, 255, 0.16);
    }
  }
}

.app-workspace.-collapsed {
  padding: 0;
  position: relative;

  > .firstletter,
  > .name {
    display: none;
  }

  > .navigation {
    border-radius: 50%;
    position: absolute;
    top: 12px;
    background-color: rgba(255, 255, 255, 0.16);
    left: 4px;
  }
}
</style>
