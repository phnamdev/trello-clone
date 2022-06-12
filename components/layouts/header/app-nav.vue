<template>
  <div class="app-nav">
    <app-button
      v-for="item in menuItems"
      :key="item.id"
      class="nav-link"
      rounded
    >
      {{ item.label }}
      <template #append>
        <caret-down-icon class="icon" />
      </template>
    </app-button>
  </div>
</template>

<script>
import CaretDownIcon from '@/assets/image/icon/caret-down.svg?inline'

export default {
  components: {
    CaretDownIcon,
  },

  data() {
    return {
      menuItems: [
        {
          id: 'workspace',
          label: 'Workspaces',
        },
        {
          id: 'recent',
          label: 'Recent',
        },
        {
          id: 'starred',
          label: 'Starred',
        },
        {
          id: 'template',
          label: 'Templates',
        },
      ],
    }
  },
}
</script>

<style lang="scss">
.app-nav {
  margin: 0 4px;

  .nav-link {
    background-color: rgba(0, 0, 0, 0);
    color: #fff;
    margin-right: 4px;

    &:hover {
      background-color: rgba(255, 255, 255, 0.3);
      color: #fff;
      opacity: 1 !important;
    }

    .icon {
      width: 16px;
      height: 16px;
      line-height: 16px;
      vertical-align: middle;
    }
  }
}
</style>
