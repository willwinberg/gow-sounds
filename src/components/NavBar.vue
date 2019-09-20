<template>
  <nav>
    <v-app-bar app>
      <v-app-bar-nav-icon @click="drawer = !drawer" />
      <v-toolbar-title>
        <span class="font-weight-black">GOW</span>
        <span class="font-weight-light">Sounds</span>
      </v-toolbar-title>
    </v-app-bar>
    <v-navigation-drawer app v-model="drawer">
      <v-list shaped dense>
        <v-list-item-group v-model="item" color="danger">
          <v-list-item @click="navigate('/')">
            <v-list-item-action>
              <v-list-item-icon>
                <v-icon>mdi-home</v-icon>
              </v-list-item-icon>
            </v-list-item-action>
            <v-list-item-content>
              <v-list-item-title>Home</v-list-item-title>
            </v-list-item-content>
          </v-list-item>

            <v-list-item @click="navigate('/character')">
                <v-list-item-action>
                    <v-list-item-icon>
                        <v-icon>mdi-face</v-icon>
                    </v-list-item-icon>
                </v-list-item-action>
                <v-list-item-content>
                    <v-list-item-title>Change Character</v-list-item-title>
                </v-list-item-content>
            </v-list-item>

            <v-list-item @click="navigate('/about')">
                <v-list-item-action>
                    <v-list-item-icon>
                        <v-icon>mdi-information</v-icon>
                    </v-list-item-icon>
                </v-list-item-action>
                <v-list-item-content>
                    <v-list-item-title>About</v-list-item-title>
                </v-list-item-content>
            </v-list-item>

        </v-list-item-group>
      </v-list>
    </v-navigation-drawer>
  </nav>
</template>

<script>
export default {
  name: "NavBar",
  data: () => ({
    item: 0,
    // items: [],
    drawer: false
  }),
    methods: {
      navigate: function(route) { this.$router.push(route) }
    }
};
</script>
