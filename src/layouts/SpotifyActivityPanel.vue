<template>
  <div class="SpotifyActivityPanel">
    <h2>
      Friend Activity
    </h2>

    <ActivityBox
      name="iqbal"
      :isPlaying="true"
      songTitle="GDFR (feat. Sage Gemini & Lookas [Remixes])"
      songArtist="Flo Rida"
      songResource="GDFR (feat. Sage Gemini & Lookas [Remixes])" />

    <ActivityBox
      name="Lucky"
      :isPlaying="false"
      lastPlaying="9h"
      songTitle="Cigaro"
      songArtist="System Of A Down"
      songResource="Hell Yeaahh" />

    <Button text="Find Friends" />
  </div>
</template>

<script>
import ActivityBox from '@/components/ActivityBox';
import Button from '@/components/Button';

export default {
  name: 'SpotifyActivityPanel',

  components: {
    ActivityBox,
    Button,
  },
}
</script>

<style lang="scss">
// Mixins
@mixin panelMixin($bgcolor, $area) {
  grid-area: #{$area};
  
  color: var(--white-alt);
  background: #{$bgcolor};
}

.SpotifyActivityPanel {
  @include panelMixin('#121212', activity);
  padding: 1rem;
  text-align: center;

  h2 {
    color: var(--white);
    font-size: 1rem;
    text-align: left;

    padding-bottom: 0.5em;
    border-bottom: 1px solid var(--white-shade);
  }
}
</style>