<template>
  <div class="AlbumCover" ref="AlbumCover">
    <div class="AlbumCover--Dropdown" @click="hideAlbumCover">
      <img src="../assets/icons/dropdown.svg" class="Dropdown-Icon">
    </div>
  </div>
</template>

<script>
export default {
  name: 'AlbumCover',

  mounted: function () {
    this.eventBus.$on('showAlbumCover', () => this.showAlbumCover());
  },

  methods: {
    showAlbumCover: function () {
      this.$refs.AlbumCover.style.paddingTop = '100%';
    },

    hideAlbumCover: function () {
      this.$refs.AlbumCover.style.padding = '0';
      this.eventBus.$emit('hideAlbumCover');
    }
  }
}
</script>

<style lang="scss">
.AlbumCover {
  position: relative;

  width: 100%;

  background: url('../assets/covers/album.jpeg') center center/cover;

  transition: .4s ease-out;

  &:hover &--Dropdown {
    opacity: 1;
  }

  &--Dropdown {
    opacity: 0;
    
    position: absolute;
    top: .25rem;
    right: .25rem;

    width: 1.5rem;
    height: 1.5rem;

    display: flex;
    align-items: center;
    justify-content: center;

    border-radius: 50%;
    background: rgba(0, 0, 0, 0.75);

    cursor: pointer;
    transition: .4s ease-out;
  }
}
</style>