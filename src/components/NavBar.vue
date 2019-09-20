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
        <v-list-item-group v-model="character" color="primary">
          <v-list-item
            v-for="(character, i) in characters"
            :key="i"
            @click="navigate(character.path)"
          >
            <v-list-item-avatar>
              <v-img :src="character.avatar"></v-img>
            </v-list-item-avatar>
            <v-list-item-content>
              <v-list-item-title center v-text="character.name"></v-list-item-title>
            </v-list-item-content>
              <v-list-item-avatar>
                  <v-img :src="character.icon"></v-img>
              </v-list-item-avatar>
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
    character: 0,
    characters: [],
    drawer: false
  }),
  created: function() {
    this.makeCharacters();
  },
  methods: {
    navigate: function(route) {
      console.log(this.characters);
      this.$router.push(route);
    },
    makeCharacters: function() {
      const cogs = ["Marcus", "Carmine"];
      const locusts = ["Myrrah", "Grub"];
      const characterNames = cogs.concat(locusts);

      this.characters = characterNames.map(name => ({
        name,
        avatar: require(`@/assets/avatars/${name.toLowerCase()}.jpg`),
        icon: require(`@/assets/${cogs.includes(name) ? "cog" : "horde"}.png`),
        path: `/${name.toLowerCase()}`
      }));
    }
  }
};
</script>
