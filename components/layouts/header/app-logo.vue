<template>
  <nuxt-link to="/" class="link">
    <logo-icon class="icon" />
  </nuxt-link>
</template>

<script>
import LogoIcon from '@/assets/image/icon/logo.svg?inline'

export default {
  name: 'AppLogo',

  components: {
    LogoIcon,
  },
}
</script>

<style lang="scss">
.link {
  padding: 0 6px;
  height: 32px;
  border-radius: 4px;

  &:hover {
    background-color: rgba(255, 255, 255, 0.2);
  }

  .icon {
    width: 75px;
    height: 32px;
  }
}
</style>
