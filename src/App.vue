<template>
  <v-app>
    <component v-bind:is="layout"></component>
    <v-footer :fixed="fixed" app>
      <div class="pa-3">&copy; Stats off 2017</div>
    </v-footer>
  </v-app>
</template>

<script>
import Default from './components/layouts/DefaultLayout'
import SideBarLayout from './components/layouts/SideBarLayout'

export default {
  data () {
    return {
      fixed: false,
      title: 'Stats Off'
    }
  },
  name: 'App',
  computed: {
    layout () {
      return this.$store.getters.layout
    }
  },
  components: {
    'sidebar-layout': SideBarLayout,
    'default-layout': Default
    // define as many layouts you want for the application
  }
}
</script>
