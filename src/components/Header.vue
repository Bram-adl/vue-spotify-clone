<template>
  <div class="Header">
    <div class="Header-Control">
      <Control />
      <SearchInput />
    </div>

    <div class="Header-Profile">
      <Avatar />
      <Dropdown :dropdown="dropdown" @toggledDropdown="toggleDropdown" />
    </div>
  </div>
</template>

<script>
import Control from '@/components/Control';
import SearchInput from '@/components/SearchInput';
import Avatar from '@/components/Avatar';
import Dropdown from '@/components/Dropdown';

export default {
  name: 'Header',

  components: {
    Control,
    SearchInput,
    Avatar,
    Dropdown,
  },

  data: function () {
    return {
      dropdown: false,
    };
  },

  methods: {
    toggleDropdown: function () {
      this.dropdown = this.dropdown ? false : true;
    }
  }
}
</script>

<style lang="scss">
.Header {
  display: flex;
  align-items: center;
  justify-content: space-between;
  padding: .5rem 1.25rem;

  &-Control {
    display: flex;
    align-items: center;
    justify-content: center;
  }

  &-Profile {
    display: flex;
    align-items: center;
    justify-content: flex-end;
  }
}
</style>