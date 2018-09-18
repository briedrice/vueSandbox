<template>
  <v-container fluid>
    <v-navigation-drawer
      persistent
      :mini-variant="miniVariant"
      :clipped="clipped"
      v-model="sideNav"
      enable-resize-watcher
      fixed
      app
    >
      <v-list>
        <v-list-tile
          value="true"
          v-for="(item, i) in menuItems"
          :key="i"
        >
          <v-list-tile-action>
            <v-icon v-html="item.icon"></v-icon>
          </v-list-tile-action>
          <v-list-tile-content>
            <v-list-tile-title v-text="item.title"></v-list-tile-title>
          </v-list-tile-content>
        </v-list-tile>
      </v-list>
    </v-navigation-drawer>
    <v-toolbar
      app
      :clipped-left="clipped"
    >
      <v-toolbar-side-icon  class="hidden-lg-and-up" @click.native.stop="sideNav = !sideNav"></v-toolbar-side-icon>
      <v-btn icon @click.native.stop="miniVariant = !miniVariant" class="hidden-md-and-down">
        <v-icon v-html="miniVariant ? 'chevron_right' : 'chevron_left'"></v-icon>
      </v-btn>
      <v-toolbar-title v-text="title" class="display-1"></v-toolbar-title>
      <v-spacer></v-spacer>
    </v-toolbar>
    <v-content>
      <router-view></router-view>
    </v-content>
  </v-container>
</template>


<script>
export default {
  data () {
    return {
      clipped: false,
      sideNav: true,
      miniVariant: false,
      title: 'StatsOff-admin',
      menuItems: [
        {icon: 'lock', title: 'Log out'}
      ]
    }
  }
}
</script>

