<template>
  <div class="SpotifyMainPanel">
    <Header />
    <AdsBanner />

    <content-box title="Shortcuts">
      <MusicCard label="On Repeat" desc="The songs you can't get enough of right now." />
      
      <MusicCard label="Harry Styles" desc="Harry Styles" />
      
      <MusicCard label="Daily Mix 1" desc="Katy perry, The Vamps, Baby Ariel and more" />

      <MusicCard label="Indie Pop" desc="New and approved indie pop. Cover: Beach Bunny" detail="1,401,797 Followers" />
    </content-box>

    <content-box title="Recently Played">
      <MusicCard label="On Repeat" />
      
      <MusicCard label="On Repeat" />
      
      <MusicCard label="On Repeat" />
      
      <MusicCard label="On Repeat" />
    </content-box>
  </div>
</template>

<script>
import Header from '@/components/Header';
import AdsBanner from '@/components/AdsBanner';
import ContentBox from '@/components/ContentBox';
import MusicCard from '@/components/MusicCard';

export default {
  name: 'SpotifyMainPanel',

  components: {
    Header,
    AdsBanner,
    ContentBox,
    MusicCard,
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

.SpotifyMainPanel {
  @include panelMixin('#181818', main);
  
  width: 100%;
  height: 100%;

  overflow: auto;
}
</style>