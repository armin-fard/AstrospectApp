<template>
  <v-app id="inspire" dark>
    <v-navigation-drawer
      v-model="drawer"
      clipped
      fixed
      app
    >
      <v-list dense>
        <v-list-tile>
          <v-list-tile-action>
            <v-icon>dashboard</v-icon>
          </v-list-tile-action>
          <v-list-tile-content>
            <v-list-tile-title>Dashboard</v-list-tile-title>
          </v-list-tile-content>
        </v-list-tile>
        <v-list-tile>
          <v-list-tile-action>
            <v-icon>settings</v-icon>
          </v-list-tile-action>
          <v-list-tile-content>
            <v-list-tile-title>Media</v-list-tile-title>
          </v-list-tile-content>
        </v-list-tile>
      </v-list>
    </v-navigation-drawer>
    <v-toolbar app fixed clipped-left>
      <v-toolbar-side-icon @click.stop="drawer = !drawer"></v-toolbar-side-icon>
      <v-toolbar-title>Astrospect</v-toolbar-title>
    </v-toolbar>
    <v-content>
      <v-container fluid fill-height>
        <v-layout v-layout align-center justify-center column fill-height>
          <v-flex
            xs12
            md12
          >
            <v-layout>
              <transition name="slide-fade" appear>
                <v-avatar
                  v-if="show"
                  :tile=false
                  :size=260
                  color="grey lighten-4"
                >
                  <img src="@/assets/astrospect_logo.jpg" alt="avatar">
                </v-avatar>
              </transition>
            </v-layout>
          </v-flex>
          <transition name="slide-fade" appear>
            <v-flex
              xs5
              md12
            >
              <v-card dark color="secondary">
                <v-card-text >
                  <p class="text-xs-center">
                    This is the official webpage for Europa's first travelling artist colony.
                  </p>
                </v-card-text>
              </v-card>
            </v-flex>
          </transition>
        </v-layout>
      </v-container>
    </v-content>
    <v-footer app fixed>
      <span>Atrospect. &copy; 2093</span>
    </v-footer>
  </v-app>
</template>

<script>
  export default {
    data: () => ({
      drawer: false,
      show: false
    }),
    props: {
      source: String
    },
    created () {
      this.show = true
    }
  }
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
.slide-fade-enter-active {
  transition: all 1s ease;
}
.slide-fade-leave-active {
  transition: all .8s cubic-bezier(1.0, 0.5, 0.8, 1.0);
}
.slide-fade-enter, .slide-fade-leave-to
/* .slide-fade-leave-active below version 2.1.8 */ {
  transform: translateX(10px);
  opacity: 0;
}
</style>
