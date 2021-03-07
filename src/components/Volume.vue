<template>
  <div class="Volume">
    <slot></slot>
    <div class="Volume-Slider" :style="{ '--width': (value/max) * 100  + '%' }" ref="VolumeSlider">
      <input type="range" class="Slider" v-model="volume" min="0" :max="max" @input="adjustVolume">
    </div>
  </div>
</template>

<script>
export default {
  name: 'Volume',

  props: {
    max: {
      type: Number,
      required: false,
    },

    min: {
      type: Number,
      required: false,
    },

    value: {
      type: Number,
      required: false,
    }
  },

  data: function () {
    return {
      volume: this.value,
    };
  },

  methods: {
    adjustVolume: function () {
      this.$refs.VolumeSlider.style.setProperty('--width', `${(this.volume / this.max) * 100}%`);
    }
  }
}
</script>

<style lang="scss">
.Volume {
  width: 100%;
  
  display: flex;
  align-items: center;
  justify-content: flex-start;

  .volume-svg {
    margin-right: 0.5rem;
    
    &:hover {
      path:not(.volume-stroke) {
        fill: var(--white);
      }

      path.volume-stroke {
        stroke: var(--white);
      }
    }
  }

  .Volume-Slider {
    line-height: 0;
    height: 3px;
    border-radius: 100px;
    position: relative;
    width: 100%;

    &:hover::after {
      background: var(--green);
    }

    &::after {
      content: "";
      position: absolute;
      left: 0;
      top: 50%;
      transform: translateY(-50%);
      width: var(--width);
      height: 3px;
      border-radius: 100px;
    }

    &::before {
      content: "";
      position: absolute;
      left: 0;
      top: 50%;
      transform: translateY(-50%);
      width: var(--width);
      height: 3px;
      background: var(--white-alt);
      border-radius: 100px;
    }

    &:hover .Slider::-webkit-slider-thumb {
      opacity: 1;
    }

    .Slider {
      position: relative;
      z-index: 2;
      
      appearance: none;
      outline: none;
      border: none;
      
      width: 100%;
      
      height: 4px;
      border-radius: 100px;

      background: var(--white-shade);
      cursor: pointer;

      &::-webkit-slider-thumb {
        appearance: none;
        width: .6rem;
        height: .6rem;
        border-radius: 100%;
        background: var(--white);
        opacity: 0;
      }
    }
  }
}
</style>