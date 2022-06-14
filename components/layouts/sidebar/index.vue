<template>
  <aside :class="['app-sidebar', { '-collapsed': !isExpand }]">
    <workspace name="eFarm" :is-expand.sync="isExpand" />
  </aside>
</template>

<script>
export default {
  name: 'LayoutSidebar',

  data() {
    return {
      isExpand: true,
    }
  },
}
</script>

<style lang="scss">
.app-sidebar {
  width: 260px;
  background-color: #b0782d;

  &.-collapsed {
    width: 16px;
    padding: 0;
    background-color: rgba(255, 255, 255, 0.16);
  }
}
</style>
