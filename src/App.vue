<template>
  <div id="app">
    <MusicPlayer
      :songList="songList"
      :musicIndex="musicIndex"
      @nextPressed="nextHandler"
      @previousPressed="previousHandler"
      @playPressed="playHandler"
    />
  </div>
</template>

<script>
import MusicPlayer from "./components/MusicPlayer.vue";

export default {
  name: "App",
  components: {
    MusicPlayer
  },
  data() {
    return {
      playState: false,
      musicIndex: 0,
      songList: [
        {
          title: "Dissolve",
          artist: "Absofacto",
          duration: "3:44",
          image: "https://i.imgur.com/Z9aaj5X.png"
        },
        {
          title: "One More Time",
          artist: "Marc Rebillet",
          duration: "3:33",
          image: "https://i.imgur.com/Xw2EieI.png"
        },
        {
          title: "SUGAR",
          artist: "BROCKHAMPTON",
          duration: "3:24",
          image: "https://i.imgur.com/KzJsVQH.png"
        },
        {
          title: "Arty Boy - Tennyson Remix",
          artist: "Flight Facilities, Emma Louise, Tennyson",
          duration: "2:23",
          image: "https://i.imgur.com/ZdWfa1C.jpg"
        }
      ]
    };
  },
  methods: {
    nextHandler() {
      this.musicIndex === this.songList.length - 1
        ? (this.musicIndex = 0)
        : this.musicIndex++;
    },
    previousHandler() {
      this.musicIndex === 0
        ? (this.musicIndex = this.songList.length - 1)
        : this.musicIndex--;
    }
  }
};
</script>

<style lang="scss">
@import "src/assets/css/app.scss";
</style>
