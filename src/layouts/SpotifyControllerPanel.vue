<template>
  <div class="SpotifyControllerPanel">
    <div class="Song-Details">
      <div class="Song-Album" ref="SongAlbum">
        <img src="../assets/covers/album.jpeg" class="Cover">
        <img src="../assets/icons/dropdown.svg" class="Dropdown-Icon" @click="showAlbumCover">
      </div>

      <SongDetail
        title="Heather"
        artist="Conan Gray" />
    </div>

    <div class="Song-Player">
      <div class="Player-Bar">
        <div class="Shuffle">
          <svg width="16" height="11" viewBox="0 0 16 11" fill="none" xmlns="http://www.w3.org/2000/svg">
            <path d="M12 4V0L15.5 2L12 4Z" fill="#B3B3B3"/>
            <path fill-rule="evenodd" clip-rule="evenodd" d="M10.7581 2.77681C9.80226 3.09543 8.67449 3.77152 7.94721 5.22608C7.0953 6.9299 5.76806 8.12062 4.46525 8.88388C3.17363 9.64059 1.86176 10.0025 1 10.0025C0.723856 10.0025 0.499999 9.77861 0.5 9.50247C0.500001 9.22633 0.723859 9.00247 1 9.00247C1.63824 9.00247 2.77637 8.71435 3.95975 8.02106C5.13194 7.33432 6.3047 6.27504 7.05279 4.77886C7.92551 3.03341 9.29774 2.20951 10.4419 1.82813C11.0112 1.63837 11.5253 1.55719 11.8985 1.52327C12.0855 1.50627 12.2384 1.50102 12.3467 1.50014C12.4009 1.4997 12.4441 1.50035 12.4749 1.50119C12.4904 1.5016 12.5027 1.50207 12.5118 1.50246L12.5231 1.50299L12.5268 1.50319L12.5283 1.50327L12.5289 1.5033C12.5291 1.50332 12.5294 1.50333 12.5 2.00247L12.5294 1.50333C12.805 1.51955 13.0154 1.75616 12.9991 2.03183C12.9829 2.30706 12.7471 2.51716 12.4719 2.50168C12.4719 2.50168 12.4719 2.50168 12.4719 2.50168C12.4718 2.50167 12.4716 2.50166 12.4714 2.50165L12.4711 2.50163C12.4709 2.50162 12.4708 2.50161 12.4706 2.50161L12.4686 2.50152L12.4479 2.50082C12.4282 2.50029 12.3967 2.49977 12.3548 2.50011C12.271 2.50079 12.1458 2.50492 11.989 2.51917C11.6747 2.54774 11.2388 2.61657 10.7581 2.77681Z" fill="#B3B3B3"/>
            <path fill-rule="evenodd" clip-rule="evenodd" d="M10.689 8.03587C10.2415 7.97575 9.58123 7.7656 8.82463 7.11975C8.61461 6.94046 8.29901 6.96538 8.11972 7.17541C7.94044 7.38543 7.96536 7.70103 8.17538 7.88032C9.07876 8.65147 9.91841 8.94133 10.5559 9.02696C10.872 9.06942 11.1326 9.06094 11.3202 9.03996C11.414 9.02947 11.4896 9.01584 11.5449 9.00387C11.5726 8.99788 11.5952 8.99229 11.6126 8.98769L11.6346 8.98161L11.6426 8.97927L11.6458 8.97829L11.6472 8.97785L11.6479 8.97765C11.6482 8.97755 11.6485 8.97745 11.501 8.50342L11.6485 8.97745C11.9122 8.8954 12.0594 8.61513 11.9773 8.35146C11.8959 8.08973 11.6191 7.94273 11.3571 8.02086C11.3552 8.02143 11.3533 8.02202 11.3513 8.02262L11.4999 8.50004C11.3513 8.02262 11.3516 8.02253 11.3519 8.02244L11.3525 8.02226L11.3536 8.02194L11.3553 8.02141" fill="#B3B3B3"/>
            <path d="M11 6.50244V10.5024L14.5 8.50244L11 6.50244Z" fill="#B3B3B3"/>
            <path fill-rule="evenodd" clip-rule="evenodd" d="M6.0347 4.46305C6.21628 4.255 6.19482 3.93915 5.98678 3.75757C4.25778 2.24852 2.18542 1.62856 1.05526 1.50298C0.780806 1.47249 0.533597 1.67026 0.503102 1.94471C0.472607 2.21916 0.670375 2.46637 0.944828 2.49687C1.90788 2.60387 3.77871 3.1577 5.32922 4.51097C5.53726 4.69255 5.85312 4.6711 6.0347 4.46305Z" fill="#B3B3B3"/>
          </svg>
        </div>
        <div class="Before">
          <svg width="10" height="11" viewBox="0 0 10 11" fill="none" xmlns="http://www.w3.org/2000/svg">
            <path d="M2.5 4.5L10 0V11L2.5 6.5V10.5H0V0.5H2.5V4.5Z" fill="#B3B3B3"/>
          </svg>
        </div>
        <div class="Pause-Start">
          <svg width="10" height="12" viewBox="0 0 10 12" fill="none" xmlns="http://www.w3.org/2000/svg" v-if="pause">
            <rect width="3" height="12" fill="white"/>
            <rect x="7" width="3" height="12" fill="white"/>
          </svg>
          <svg width="21" height="20" viewBox="0 0 21 20" fill="none" xmlns="http://www.w3.org/2000/svg" v-else>
            <path d="M15.5 10.1962L6.5 15.3923L6.5 5L15.5 10.1962Z" fill="white"/>
          </svg>
        </div>
        <div class="After">
          <svg width="10" height="11" viewBox="0 0 10 11" fill="none" xmlns="http://www.w3.org/2000/svg">
            <path d="M7.5 4.5L0 0V11L7.5 6.5V10.5H10V0.5H7.5V4.5Z" fill="#B3B3B3"/>
          </svg>
        </div>
        <div class="Repeat">
          <svg width="15" height="12" viewBox="0 0 15 12" fill="none" xmlns="http://www.w3.org/2000/svg">
            <path d="M9.5 4V0L13 2L9.5 4Z" fill="#B3B3B3"/>
            <path fill-rule="evenodd" clip-rule="evenodd" d="M1.74144 3.10282C2.58537 1.83038 4.11987 1.5 5.43889 1.5H9.5C9.77614 1.5 10 1.72386 10 2C10 2.27614 9.77614 2.5 9.5 2.5H5.43889C4.22049 2.5 3.13335 2.81338 2.5748 3.65554C2.00775 4.51051 1.5 5.78258 1.5 7.5C1.5 7.77614 1.27614 8 1 8C0.723858 8 0.5 7.77614 0.5 7.5C0.5 5.57609 1.0713 4.11322 1.74144 3.10282Z" fill="#B3B3B3"/>
            <path d="M5.5 8V12L2 10L5.5 8Z" fill="#B3B3B3"/>
            <path fill-rule="evenodd" clip-rule="evenodd" d="M13.2586 8.89718C12.4146 10.1696 10.8801 10.5 9.56111 10.5H5.5C5.22386 10.5 5 10.2761 5 10C5 9.72386 5.22386 9.5 5.5 9.5H9.56111C10.7795 9.5 11.8666 9.18662 12.4252 8.34446C12.9923 7.48949 13.5 6.21742 13.5 4.5C13.5 4.22386 13.7239 4 14 4C14.2761 4 14.5 4.22386 14.5 4.5C14.5 6.42391 13.9287 7.88678 13.2586 8.89718Z" fill="#B3B3B3"/>
          </svg>
        </div>
      </div>

      <div class="Player-Time">
        <div class="Current-Time">
          1:42
        </div>
        <Volume :min="0" :max="277" :value="102" />
        <div class="Total-Time">
          4:37
        </div>
      </div>
    </div>

    <div class="Song-Controller">
      <div class="Lyric">
        <svg width="11" height="13" viewBox="0 0 11 13" fill="none" xmlns="http://www.w3.org/2000/svg">
          <path fill-rule="evenodd" clip-rule="evenodd" d="M9.23515 4C9.23515 5.65685 7.89201 7 6.23515 7C4.5783 7 3.23515 5.65685 3.23515 4C3.23515 2.34315 4.5783 1 6.23515 1C7.89201 1 9.23515 2.34315 9.23515 4ZM6.59568 7.98397C8.63589 7.80171 10.2352 6.08762 10.2352 4C10.2352 1.79086 8.44429 0 6.23515 0C4.02601 0 2.23515 1.79086 2.23515 4C2.23515 4.32643 2.27425 4.64373 2.34803 4.94746L0.143333 10.3204L0.143216 10.3207L0.143162 10.3208C-0.219195 11.2025 0.126498 12.2164 0.952097 12.693C1.77782 13.1698 2.82888 12.9621 3.41124 12.2071L3.41126 12.2071L3.41509 12.2021L6.59568 7.98397ZM5.22891 7.87237C4.32886 7.63916 3.55184 7.10044 3.01511 6.37349L1.21494 10.7606L1.21477 10.761C1.07282 11.1062 1.20812 11.5031 1.53134 11.6897C1.85377 11.8759 2.26397 11.7954 2.49226 11.5017L5.22891 7.87237Z" fill="#B3B3B3"/>
        </svg>
      </div>

      <div class="Queue">
        <svg width="14" height="12" viewBox="0 0 14 12" fill="none" xmlns="http://www.w3.org/2000/svg">
          <path d="M0 5V0L4 2.5L0 5Z" fill="#B3B3B3"/>
          <rect x="7" y="3" width="7" height="1" fill="#C4C4C4"/>
          <rect y="7" width="14" height="1" fill="#C4C4C4"/>
          <rect y="11" width="14" height="1" fill="#C4C4C4"/>
        </svg>
      </div>

      <div class="Connect">
        <svg width="16" height="13" viewBox="0 0 16 13" fill="none" xmlns="http://www.w3.org/2000/svg">
          <rect width="6" height="1" fill="#C4C4C4"/>
          <rect x="8" y="12" width="8" height="1" fill="#C4C4C4"/>
          <path fill-rule="evenodd" clip-rule="evenodd" d="M14 0H8V1V12H9L9 1H14V0Z" fill="#C4C4C4"/>
          <rect x="16" y="1" width="11" height="1" transform="rotate(90 16 1)" fill="#C4C4C4"/>
          <rect x="1" y="1" width="9" height="1" transform="rotate(90 1 1)" fill="#C4C4C4"/>
          <rect x="6" y="10" width="5" height="1" transform="rotate(-180 6 10)" fill="#C4C4C4"/>
          <rect x="6" y="13" width="3" height="1" transform="rotate(-180 6 13)" fill="#C4C4C4"/>
          <circle cx="12" cy="3" r="1" fill="#C4C4C4"/>
          <path fill-rule="evenodd" clip-rule="evenodd" d="M12 9C12.5523 9 13 8.55228 13 8C13 7.44772 12.5523 7 12 7C11.4477 7 11 7.44772 11 8C11 8.55228 11.4477 9 12 9ZM12 10C13.1046 10 14 9.10457 14 8C14 6.89543 13.1046 6 12 6C10.8954 6 10 6.89543 10 8C10 9.10457 10.8954 10 12 10Z" fill="#C4C4C4"/>
        </svg>
      </div>

      <volume :min="0" :max="100" :value="100">
        <svg width="16" height="14" viewBox="0 0 16 14" fill="none" xmlns="http://www.w3.org/2000/svg" class="volume-svg">
          <path d="M0.5 9.5V4.5H3.5L7.5 1.5V12.5L3.5 9.5H0.5Z" stroke="#AFAFAF" class="volume-stroke" />
          <path fill-rule="evenodd" clip-rule="evenodd" d="M11.2803 6.03489C11.1236 4.964 10.5877 4.22393 10.1799 3.8841L10.8201 3.11588C11.4123 3.60937 12.0765 4.5693 12.2697 5.89009C12.4651 7.22494 12.1746 8.88947 10.916 10.7773L10.084 10.2226C11.2254 8.5105 11.4349 7.0917 11.2803 6.03489Z" fill="#AFAFAF"/>
          <path fill-rule="evenodd" clip-rule="evenodd" d="M12.5789 12.7304C16.069 7.27955 13.9916 3.5224 12.6723 2.37766L13.3276 1.62234C15.0268 3.09665 17.1753 7.40617 13.421 13.2696L12.5789 12.7304Z" fill="#AFAFAF"/>
        </svg>
      </volume>
    </div>
  </div>
</template>

<script>
import SongDetail from '@/components/SongDetail';
import Volume from '@/components/Volume';

export default {
  name: 'SpotifyControllerPanel',

  components: {
    SongDetail,
    Volume,
  },

  data: function () {
    return {
      pause: false,
    }
  },

  mounted: function () {
    this.eventBus.$on('hideAlbumCover', () => this.hideAlbumCover());
  },

  methods: {
    showAlbumCover: function () {
      this.$refs.SongAlbum.style.marginLeft = '-4rem';
      this.eventBus.$emit('showAlbumCover');
    },
    
    hideAlbumCover: function () {
      this.$refs.SongAlbum.style.marginLeft = '0';
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

.SpotifyControllerPanel {
  @include panelMixin('#282828', controller);

  display: flex;
  align-items: center;
  justify-content: space-between;

  padding: 0 1rem;
}

.Song-Details {
  display: flex;
  align-items: center;
  justify-content: flex-start;

  .Song-Album {
    line-height: 0;
    margin-right: 1rem;
    position: relative;
    transition: .4s ease-out;

    &:hover .Dropdown-Icon {
      opacity: 1;
    }

    .Cover {
      width: 3rem;
      height: 3rem;
      object-fit: cover;
    }

    .Dropdown-Icon {
      opacity: 0;
      
      position: absolute;
      right: .25rem;
      top: .25rem;

      background: rgba(0, 0, 0, 0.5);
      
      width: 1.5rem;
      height: 1.5rem;
      padding: .3rem;
      border-radius: 50%;

      transform: rotate(180deg);
      cursor: pointer;
      transition: .4s ease-out;
    }
  }
}

.Song-Player {
  flex: 1;
  padding: 0 8rem;
  
  .Player-Bar {
    display: flex;
    align-items: center;
    justify-content: center;

    .Shuffle,
    .Before,
    .Pause-Start,
    .After,
    .Repeat {
      margin: 0 1rem;
      cursor: pointer;

      &:hover {
        svg rect,
        svg path {
          fill: var(--white);
        }
      }
    }

    .Pause-Start:hover {
      transform: scale(1.1);
    }

    .Pause-Start {
      border: 1px solid var(--white);
      border-radius: 50%;
      width: 2rem;
      height: 2rem;
      display: flex;
      align-items: center;
      justify-content: center;
    }
  }

  .Player-Time {    
    margin-top: .5rem;
    width: 100%;

    display: flex;
    align-items: center;
    justify-content: space-between;

    .Current-Time,
    .Total-Time {
      font-size: 0.7rem;
      margin: 0 1rem;
    }
  }
}

.Song-Controller {
  display: flex;
  align-items: center;
  justify-content: center;

  .Lyric,
  .Queue,
  .Connect,
  .Volume {
    margin: 0 .75rem;

    cursor: pointer;

    &:hover {

      svg:not(.volume-svg) path,
      svg:not(.volume-svg) circle,
      svg:not(.volume-svg) rect {
        fill: var(--white);
      }
    }
  }
}
</style>