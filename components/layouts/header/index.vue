<template>
  <nav class="app-header">
    <more-app />
    <app-logo />
    <app-nav />
    <app-button rounded class="button -create">Create</app-button>
    <div class="space"></div>
    <app-search class="search" />
    <app-button rounded class="action">
      <infomation-logo width="20" height="20" />
    </app-button>
    <app-button rounded class="action">
      <notification-logo width="20" height="20" />
    </app-button>
    <app-button rounded class="user" title="phnam">
      <img
        class="avatar"
        src="https://avatars.githubusercontent.com/u/27210588?s=40&v=4"
      />
    </app-button>
  </nav>
</template>

<script>
import MoreApp from './more-app'
import AppLogo from './app-logo'
import AppNav from './app-nav'
import AppSearch from './app-search'
import InfomationLogo from '@/assets/image/icon/information.svg?inline'
import NotificationLogo from '@/assets/image/icon/notification.svg?inline'

export default {
  name: 'LayoutHeader',

  components: {
    MoreApp,
    AppLogo,
    AppNav,
    AppSearch,
    InfomationLogo,
    NotificationLogo,
  },
}
</script>

<style lang="scss">
.app-header {
  display: flex;
  align-items: center;
  height: var(--app-header-height);
  background-color: var(--dynamic-background-color, #b0782d);
  padding: 6px 4px;

  > .button.-create {
    background-color: rgba(255, 255, 255, 0.2);
    color: #fff;
    margin: 0 4px;
  }

  > .space {
    flex: 1;
  }

  > .search {
    margin: 0 4px;
  }

  > .action {
    padding: 6px 6px;
    background-color: transparent;
    color: #fff;
    margin-right: 4px;

    &:hover {
      background-color: rgba(255, 255, 255, 0.2);
    }
  }

  > .user {
    padding: 0;
    background-color: transparent;

    &:hover {
      opacity: 1;
    }

    > .avatar {
      width: 32px;
      height: 32px;
      border-radius: 50%;
    }
  }
}
</style>
