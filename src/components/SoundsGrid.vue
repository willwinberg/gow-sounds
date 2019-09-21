<template>
  <v-container>
    <v-row wrap>
      <v-col xs4 v-for="(sound, i) in character.sounds" :key="i">
        <v-card @click="play(sound)">
          <v-card-text>
            <v-icon color="red" x-large>mdi-play</v-icon>
            {{sound}}
          </v-card-text>
        </v-card>
      </v-col>
    </v-row>
  </v-container>
</template>

<script>
export default {
  name: "SoundsGrid",
  data: () => ({
    character: {
      name: 'marcus',
      sounds: ['nice', 'nice3', 'keepmoving', 'youcanmakeit', 'sweet']
    }
  }),
  // created: function() {
  //   this.getCharacterSounds();
  // },
  methods: {
    play: function(sound) {
        let audio = new Audio(require(`@/assets/sounds/${this.character.name}/${sound}.mp3`));
        audio.play();
    },
    // getCharacterSounds: function() {
    //   this.sounds = this.character.sounds.map(sound => {
    //     return {
    //       name: sound.name,
    //       sound: sound.name.toLowerCase()
    //     }
    //   });
    // }
  }
};
</script>
