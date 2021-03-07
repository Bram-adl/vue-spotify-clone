<template>
  <div class="Dropdown">
    <img src="../assets/icons/dropdown.svg" class="Dropdown-Icon" @click="toggleDropdown">

    <ul class="Dropdown-Menu" v-if="dropdown">
      <li class="Dropdown-Menu--Item">Private Session</li>
      <li class="Dropdown-Menu--Item">Account</li>
      <li class="Dropdown-Menu--Item">Upgrade Your Account</li>
      <li class="Dropdown-Menu--Item">Settings</li>
      <li class="Dropdown-Menu--Item">Log Out</li>
    </ul>
  </div>
</template>

<script>
export default {
  name: 'Dropdown',

  props: {
    dropdown: {
      type: Boolean,
      required: true,
    },
  },

  methods: {
    toggleDropdown: function () {
      this.$emit('toggledDropdown');
    },
  }
}
</script>

<style lang="scss">
.Dropdown {
  position: relative;
  
  display: flex;
  align-items: center;
  justify-content: center;

  margin-left: 1rem;

  cursor: pointer;

  &-Menu {
    position: absolute;
    right: 0;
    top: 100%;
    transform: translate(.75rem, 1.25rem);

    background: #181818;
    box-shadow: 0px 2px 8px 4px #121212;
    border-radius: .5rem;

    width: auto;
    height: auto;
    padding: .5rem 0;

    list-style-type: none;

    &::after {
        content: '';
        position: absolute;
        right: .5rem;
        bottom: 100%;

        width: 0; 
        height: 0; 
        border-left: .75rem solid transparent;
        border-right: .75rem solid transparent;
        
        border-bottom: .75rem solid #181818;
      }

    &--Item {
      min-width: 200px;
      padding: .5rem 1rem;

      font-size: .8rem;

      cursor: pointer;
      transition: .1s ease-out;

      &:hover {
        background: #404040;
        color: var(--white);
      }      
    }
  }
}
</style>