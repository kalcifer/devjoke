<template>
  <fvMain>
    <fvSidebar v-model="sidebar" class="sidebar">
      <div class="fv-text-center fv-padding">
        <fvAvatar
          name="Default User"
          src="https://randomuser.me/api/portraits/women/44.jpg"
          size="128px"
        />
        <h2 class="fv-padding-sm">
          Default User
        </h2>
      </div>
      <fvList parent>
        <fvListItem class="selected">
          <i class="material-icons">sentiment_very_satisfied</i> Welcome
        </fvListItem>
        <fvListItem disabled>
          <i class="material-icons">person</i> Profile
        </fvListItem>
        <fvListItem disabled>
          <i class="material-icons">mail</i> Messages
        </fvListItem>
        <fvListItem disabled>
          <i class="material-icons">event_available</i> Events
        </fvListItem>
        <fvListItem disabled>
          <i class="material-icons">photo</i> Pictures
        </fvListItem>
      </fvList>
    </fvSidebar>
    <fvContent>
      <fvHeader>
        <fvButton
          class="fv-margin-end fv-hidden-lg fv-hidden-xl"
          @click="toggleSidebar"
        >
          <i class="material-icons">menu</i>
        </fvButton>
        <div class="fv-margin-end">
          <div>dev Jokes</div>
        </div>
      </fvHeader>
      <div class="content fv-padding">
        <nuxt />
      </div>
    </fvContent>
  </fvMain>
</template>

<script>
export default {
  data() {
    return {
      sidebar: false,
      docsMenu: false,
      slider: 'One',
      exmps: {
        htw: 13,
        firstName: undefined,
        lastName: undefined,
        gender: 'm',
        continent: undefined,
        married: undefined,
        marriageDate: undefined,
        bio: undefined
      }
    }
  },
  methods: {
    toggleSidebar() {
      this.sidebar = !this.sidebar
    },
    toggleDocsMenu() {
      setTimeout(() => {
        this.docsMenu = !this.docsMenu
      })
    }
  }
}
</script>

<style>
html {
  font-family: 'Source Sans Pro', -apple-system, BlinkMacSystemFont, 'Segoe UI',
    Roboto, 'Helvetica Neue', Arial, sans-serif;
  font-size: 15px;
  word-spacing: 1px;
  -ms-text-size-adjust: 100%;
  -webkit-text-size-adjust: 100%;
  -moz-osx-font-smoothing: grayscale;
  -webkit-font-smoothing: antialiased;
  box-sizing: border-box;
}
*,
*:before,
*:after {
  box-sizing: border-box;
  margin: 0;
}
html,
body,
#__nuxt,
#__layout {
  min-height: 100%;
  height: 100%;
  position: initial;
}
body .material-icons {
  vertical-align: middle;
}
</style>
