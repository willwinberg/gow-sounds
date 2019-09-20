<template>
  <nav>
    <v-toolbar app>
      <v-app-bar-nav-icon @click="drawer = !drawer" />
      <v-toolbar-title>
        <span class="font-weight-black">GOW</span>
        <span class="font-weight-light">Sounds</span>
      </v-toolbar-title>
    </v-toolbar>
    <v-navigation-drawer app v-model="drawer">
      <v-list shaped>
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
        </v-list-item-group>
      </v-list>
    </v-navigation-drawer>
  </nav>
</template>

<script>
export default {
  name: "NavBar",
  data: () => ({
    // item: 1,
    // items: [],
    drawer: false
  })
};
</script>
