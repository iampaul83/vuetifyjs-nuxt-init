<template>
  <v-app>
    <!-- v-navigation-drawer -->
    <!-- v-model 控制是否開啟 -->
    <!-- mini-variant 控制 drawer 大小 -->
    <!-- clipped 會讓 drawer 在 toolbar 下面 -->
    <v-navigation-drawer app v-model="drawer" :mini-variant.sync="miniVariant" :clipped="clipped" width="250">
      <v-list>
        <!-- nuxt, to, exact 都是跟 nuxt-link 有關的 -->
        <v-list-tile v-for="(link, i) in nav_links" :key="i" nuxt :to="link.to" exact>
          <v-list-tile-action>
            <v-icon>{{ link.icon }}</v-icon>
          </v-list-tile-action>
          <v-list-tile-content>
            <v-list-tile-title>{{ link.title }}</v-list-tile-title>
          </v-list-tile-content>
        </v-list-tile>
      </v-list>
    </v-navigation-drawer>

    <!-- v-toolbar -->
    <v-toolbar app :clipped-left="clipped">
      <!-- toolbar left -->
      <v-toolbar-side-icon @click="drawer = !drawer"></v-toolbar-side-icon>
      <v-toolbar-title>{{ title }}</v-toolbar-title>

      <v-spacer></v-spacer>

      <!-- toolbar right -->
      <v-btn icon @click.stop="miniVariant = !miniVariant">
        <v-icon v-text="miniVariant ? 'chevron_right' : 'chevron_left'"></v-icon>
      </v-btn>
      <v-btn icon @click.stop="clipped = !clipped">
        <v-icon>web</v-icon>
      </v-btn>
    </v-toolbar>

    <!-- v-content -->
    <v-content>
      <v-container>
        <nuxt />
      </v-container>
    </v-content>

    <!-- footer -->
    <v-footer app absolute>
      <span>&copy; 2017</span>
    </v-footer>
  </v-app>
</template>

<script>
  export default {
    data () {
      return {
        clipped: true,
        drawer: true, // drawer 開啟狀態
        nav_links: [
          { icon: 'apps', title: 'Welcome', to: '/' },
          { icon: 'bubble_chart', title: 'Inspire', to: '/inspire' }
        ],
        miniVariant: false, // nav 使用小小的版本（只有 icon）
        title: 'Vuetify.js'
      }
    }
  }
</script>
