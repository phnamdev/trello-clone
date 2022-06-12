<template>
  <div class="app-layout">
    <layouts-header />
    <main class="main">
      <layouts-sidebar></layouts-sidebar>
      <nuxt class="content" />
    </main>
  </div>
</template>

<script>
export default {
  name: 'DefaultLayout',
}
</script>

<style lang="scss">
.app-layout {
  height: 100vh;
  width: 100%;
  display: flex;
  flex-direction: column;

  > .main {
    height: calc(100% - var(--app-header-height));
    display: flex;
    flex: 1;

    > .content {
      flex: 1;
      overflow: auto;
    }
  }
}
</style>
