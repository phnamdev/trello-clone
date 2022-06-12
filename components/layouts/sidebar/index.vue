<template>
  <aside class="app-sidebar">Sidebar</aside>
</template>

<script>
export default {
  name: 'LayoutSidebar',
}
</script>

<style lang="scss">
.app-sidebar {
  width: 260px;

  &.-collapsed {
    width: 16px;
  }
}
</style>
