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
  background-color: #b0782d;

  &.-collapsed {
    width: 16px;
  }
}
</style>
