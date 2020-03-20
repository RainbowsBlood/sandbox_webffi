<template>
  <div class="trailer-wrapper">
    <youtube :video-id="videoId" :player-vars="playerVars" />
  </div>
</template>

<script>
import Vue from 'vue'
import VueYoutube from 'vue-youtube'

Vue.use(VueYoutube)

export default {
  name: 'Trailer',
  data() {
    return {
      videoId: 'LJyOO7leO8s',
      playerVars: {
        autoplay: 1,
        rel: 0,
        color: 'white'
      }
    }
  }
}
</script>

<style>
.trailer-wrapper {
  width: 100%;
  text-align: center;
}
iframe {
  width: 100%;
  max-width: 640px; /* Also helpful. Optional. */
}
</style>
