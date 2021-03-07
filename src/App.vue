<template>
  <div id="app">
    <div class="Spotify">
      <SpotifyMenuPanel />
      <SpotifyMainPanel />
      <SpotifyActivityPanel />
      <SpotifyControllerPanel />
    </div>
  </div>
</template>

<script>
import SpotifyMenuPanel from '@/layouts/SpotifyMenuPanel';
import SpotifyMainPanel from '@/layouts/SpotifyMainPanel';
import SpotifyActivityPanel from '@/layouts/SpotifyActivityPanel';
import SpotifyControllerPanel from '@/layouts/SpotifyControllerPanel';

export default {
  name: 'App',

  components: {
    SpotifyMenuPanel,
    SpotifyMainPanel,
    SpotifyActivityPanel,
    SpotifyControllerPanel,
  },
}
</script>

<style lang="scss">
.Spotify {
  background: #535353;
  
  display: grid;
  grid-template-areas: 
    'menu main activity'
    'controller controller controller'
  ;
  grid-template-columns: 175px 1fr 250px;
  grid-template-rows: minmax(0, 1fr) 75px;

  width: 100%;
  height: 100vh;

  overflow: hidden;
}
</style>
