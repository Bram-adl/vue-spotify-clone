<template>
  <div class="SpotifyMenuPanel">
    <menu-list>
      <menu-item :active="active" text="Home" type="Item">
        <svg width="20" height="21" viewBox="0 0 20 21" fill="#FFFFFF" xmlns="http://www.w3.org/2000/svg">
        <path fill-rule="evenodd" clip-rule="evenodd" d="M10 0.414062L19.5 6.21962V21H11.5V14H8.5V21H0.5V6.21962L10 0.414062ZM1.5 6.78045V20H7.5V13H12.5V20H18.5V6.78045L10 1.58601L1.5 6.78045Z" fill="#B3B3B3"/>
        </svg>
      </menu-item>

      <menu-item :active="active" text="Browse" type="Item" style="margin: 1.25rem 0;">
        <svg width="22" height="18" viewBox="0 0 22 18" fill="none" xmlns="http://www.w3.org/2000/svg">
        <path fill-rule="evenodd" clip-rule="evenodd" d="M0.359619 3H21.6185L18.4042 18H4.10962L0.359619 3ZM1.6404 4L4.8904 17H17.5958L20.3815 4H1.6404Z" fill="#B3B3B3"/>
        <path fill-rule="evenodd" clip-rule="evenodd" d="M11 13C12.6569 13 14 11.6569 14 10C14 8.34315 12.6569 7 11 7C9.34315 7 8 8.34315 8 10C8 11.6569 9.34315 13 11 13ZM11 14C13.2091 14 15 12.2091 15 10C15 7.79086 13.2091 6 11 6C8.79086 6 7 7.79086 7 10C7 12.2091 8.79086 14 11 14Z" fill="#B3B3B3"/>
        <rect x="4" width="14" height="1" fill="#C4C4C4"/>
        </svg>
      </menu-item>

      <menu-item :active="active" text="Radio" type="Item">
        <svg width="24" height="17" viewBox="0 0 24 17" fill="none" xmlns="http://www.w3.org/2000/svg">
          <path fill-rule="evenodd" clip-rule="evenodd" d="M12 10C13.1046 10 14 9.10457 14 8C14 6.89543 13.1046 6 12 6C10.8954 6 10 6.89543 10 8C10 9.10457 10.8954 10 12 10ZM12 11C13.6569 11 15 9.65685 15 8C15 6.34315 13.6569 5 12 5C10.3431 5 9 6.34315 9 8C9 9.65685 10.3431 11 12 11Z" fill="#B3B3B3"/>
          <path fill-rule="evenodd" clip-rule="evenodd" d="M4.62816 7.00816C5.0729 4.92511 6.58314 3.37572 7.82176 2.57947L8.36251 3.42065C7.2678 4.12439 5.97803 5.47501 5.60611 7.21696C5.24374 8.9142 5.72544 11.1201 8.43236 13.6337L7.75191 14.3665C4.85883 11.68 4.17386 9.13591 4.62816 7.00816Z" fill="#B3B3B3"/>
          <path fill-rule="evenodd" clip-rule="evenodd" d="M19.464 7.00816C19.0193 4.92511 17.509 3.37572 16.2704 2.57947L15.7296 3.42065C16.8244 4.12439 18.1141 5.47501 18.486 7.21696C18.8484 8.9142 18.3667 11.1201 15.6598 13.6337L16.3403 14.3665C19.2333 11.68 19.9183 9.13591 19.464 7.00816Z" fill="#B3B3B3"/>
          <path fill-rule="evenodd" clip-rule="evenodd" d="M23.3809 6.53289C22.9656 3.79942 21.5438 1.72093 20.3353 0.629028L19.6649 1.37102C20.7203 2.32458 22.0151 4.20063 22.3922 6.68307C22.7663 9.14588 22.244 12.2494 19.6032 15.6959L20.397 16.3041C23.1894 12.6597 23.7991 9.28599 23.3809 6.53289Z" fill="#B3B3B3"/>
          <path fill-rule="evenodd" clip-rule="evenodd" d="M0.619268 6.53289C1.03451 3.79942 2.45633 1.72093 3.66483 0.629028L4.33524 1.37102C3.27986 2.32458 1.98504 4.20063 1.60793 6.68307C1.2338 9.14588 1.75609 12.2494 4.39692 15.6959L3.60315 16.3041C0.810684 12.6597 0.201041 9.28599 0.619268 6.53289Z" fill="#B3B3B3"/>
        </svg>
      </menu-item>
    </menu-list>

    <menu-list>
      <MenuItem :active="active" text="Your Library" type="Label" />
      <MenuItem :active="active" text="Made For You" type="Item" />
      <MenuItem :active="active" text="Recently Played" type="Item" />
      <MenuItem :active="active" text="Liked Songs" type="Item" />
      <MenuItem :active="active" text="Albums" type="Item" />
      <MenuItem :active="active" text="Artists" type="Item" />
      <MenuItem :active="active" text="Podcasts" type="Item" />
    </menu-list>
    
    <menu-list>
      <MenuItem :active="active" text="Playlists" type="Label" />
      <MenuItem :active="active" text="Nightingale" type="Item" />
      <MenuItem :active="active" text="Touring" type="Item" />
    </menu-list>

    <div class="SpotifyMenuPanel--Tools">
      <CreateNewPlaylist />
      <AlbumCover />
    </div>
  </div>
</template>

<script>
import MenuList from '@/components/MenuList';
import MenuItem from '@/components/MenuItem';
import CreateNewPlaylist from '@/components/CreateNewPlaylist';
import AlbumCover from '@/components/AlbumCover';

export default {
  name: 'SpotifyMenuPanel',

  components: {
    MenuList,
    MenuItem,
    CreateNewPlaylist,
    AlbumCover,
  },

  data: function () {
    return {
      active: 'Home',
    };
  },

  mounted: function () {
    this.eventBus.$on('setActive', (active) => this.setActive(active));
  },

  beforeDestroy: function () {
    this.eventBus.$off('setActive', (active) => this.setActive(active));
  },

  methods: {
    setActive: function (active) {
      this.active = active;
    },
  }
}
</script>

<style lang="scss">
// Mixins
@mixin panelMixin($bgcolor, $area) {
  grid-area: #{$area};
  
  color: var(--white-alt);
  background: #{$bgcolor};
}

.SpotifyMenuPanel {
  @include panelMixin('#121212', menu);

  position: relative;

  width: 100%;
  height: 100%;

  overflow-y: auto;

  &--Tools {
    position: absolute;
    bottom: 0;
    left: 0;

    width: 100%;
    height: auto;
  }
}
</style>