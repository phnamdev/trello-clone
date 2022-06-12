<template>
  <div class="more-app">
    <app-icon class="icon" />
  </div>
</template>

<script>
import AppIcon from '@/assets/image/icon/app.svg?inline'

export default {
  components: {
    AppIcon,
  },
}
</script>

<style lang="scss">
.more-app {
  width: 32px;
  height: 32px;
  display: inline-flex;
  justify-content: center;
  align-items: center;
  cursor: pointer;

  &:hover {
    background-color: rgba(255, 255, 255, 0.2);
  }

  > .icon {
    width: 20px;
    height: 20px;
    color: #fff;
  }
}
</style>
