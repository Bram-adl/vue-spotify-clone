<template>
  <li 
    class="MenuItem" 
    :class="[ type, active === text ? 'Active' : '' ]"
    @click="setActive"
  >
    <slot></slot>
    {{ text }}
  </li>
</template>

<script>
export default {
  name: 'MenuItem',

  props: {
    active: {
      type: String,
      required: true,
    },
    
    text: {
      type: String,
      required: true,
    },

    type: {
      type: String,
      required: false,
    },
  },

  methods: {
    setActive: function () {
      if (this.type == 'Label') return;
      this.eventBus.$emit('setActive', this.text);
    }
  }
}
</script>

<style lang="scss">
.MenuItem {
  margin: .25rem 0;

  position: relative;
  display: flex;
  align-items: center;
  justify-content: flex-start;

  &:hover svg path,
  &:hover li {
    fill: var(--white);
    color: var(--white);
  }

  svg {
    width: 2rem;
    margin-right: 1rem;
    path { transition: .1s ease-out; }
  }

  &.Label {
    font-size: .75rem;
    text-transform: uppercase;
    letter-spacing: 1px;
    margin-bottom: .5rem;
  }

  &.Item {
    font-size: .8rem;
    margin-bottom: .75rem;

    cursor: pointer;
    transition: .1s ease-out;

    &:hover {
      color: var(--white);
    }
  }

  &.Active {
    color: var(--white);

    svg path {
      fill: #FFFFFF;
    }

    &::after {
      content: "";
      position: absolute;
      top: 50%;
      left: 0;
      width: .25rem;
      height: 110%;
      transform: translate(-1rem, -50%);
      background: var(--green);
    }
  }
}
</style>