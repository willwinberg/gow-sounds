<template>
  <v-container>
    <v-layout wrap>
      <v-flex xs4 v-for="(sound, i) in sounds" :key="i">
        <v-card @click="play(sound.sound)">
          <v-card-text>
            <v-icon color="yellow" x-large>mdi-play</v-icon>
            <p>{{sound.title}}</p>
          </v-card-text>
        </v-card>
      </v-flex>
    </v-layout>
  </v-container>
</template>

<script>
export default {
  name: "SoundsGrid",
  data: () => ({
    sounds: [],
  }),
  created: function() {
    this.getCharacterSounds();
  },
  methods: {
    play: function(sound) {
        let audio = new Audio(require(`@/assets/sounds/${sound}`));
        audio.play();
    },
    getCharacterSounds: function() {

    }
  }
};
</script>
