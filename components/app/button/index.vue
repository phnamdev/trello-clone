<template>
  <button :class="buttonClass" @click="onClick">
    <span v-if="visiblePrepend" class="prepend">
      <slot name="prepend" />
    </span>
    <slot />
    <span v-if="visibleAppend" class="append">
      <slot name="append" />
    </span>
  </button>
</template>

<script>
export default {
  name: 'AppButton',

  props: {
    rounded: Boolean,

    block: Boolean,
  },

  emits: ['click'],

  computed: {
    buttonClass() {
      return {
        'app-button': true,
        '-rounded': this.rounded,
        '-block': this.block,
      }
    },

    visiblePrepend() {
      return this.$slots.prepend?.length > 0
    },

    visibleAppend() {
      return this.$slots.append?.length > 0
    },
  },

  methods: {
    onClick(event) {
      this.$emit('click', event)
    },
  },
}
</script>

<style lang="scss">
.app-button {
  outline: none;
  border: none;
  display: inline-flex;
  align-items: center;
  justify-content: center;
  padding: 6px 12px;
  font-size: 14px;
  line-height: 20px;

  &:not([disabled]) {
    cursor: pointer;

    &:hover {
      opacity: 0.75;
    }
  }

  &.-rounded {
    border-radius: 4px;
  }

  &.-block {
    display: flex;
    width: 100%;
  }

  > .prepend {
    margin-right: 4px;
  }

  > .append {
    margin-left: 4px;
  }
}
</style>
