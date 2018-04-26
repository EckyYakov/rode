<template>
  <v-app>
    <v-toolbar dark class="primary">
      <v-toolbar-side-icon 
        @click.native.stop="sideNav = !sideNav"
        class="hidden-sm-and-up"></v-toolbar-side-icon>
      <v-toolbar-title>
        <router-link to="/" tag="span" style="cursor: pointer">Rode</router-link>
      </v-toolbar-title>
      <v-spacer></v-spacer>
      <v-toolbar-items class="hidden-xs-only">
        <v-btn 
        flat v-for="item in menuItems"
        :key="item.title"
        router
        :to="item.link" :disabled="item.disabled">
          <v-icon left dark>{{ item.icon }}</v-icon>
          {{ item.title }}
        </v-btn>
      </v-toolbar-items>
    </v-toolbar>
    <main>
      <router-view></router-view>
    </main>
    <v-navigation-drawer v-model="sideNav" disable-resize-watcher=false>
      <v-list>
        <v-list-tile>
          <v-list-tile-action>
            <v-icon>dehaze</v-icon>
          </v-list-tile-action>
          <v-list-tile-content>View Projects</v-list-tile-content>
        </v-list-tile>
      </v-list>
    </v-navigation-drawer>
    <v-footer class="pa-3">
      <v-spacer></v-spacer>
      <div>&copy; {{ new Date().getFullYear() }}</div>
    </v-footer>
  </v-app>
</template>

<script>
export default {
  data () {
    return {
      sideNav: false,
      panelNumber: 3,
      menuItems: [
        { icon: 'multiline_chart', title: 'Activity', link: '/activity', disabled: false },
        { icon: 'person', title: 'Profile', link: '/profile', disabled: true },
        { icon: 'face', title: 'Sign Up', link: '/signup', disabled: true },
        { icon: 'lock_open', title: 'Sign In', link: '/signin', disabled: true }
      ]
    }
  },
  name: 'App'
}
</script>