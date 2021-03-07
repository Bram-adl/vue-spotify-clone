<template>
  <ul class="MenuList">
    <slot></slot>
  </ul>
</template>

<script>
export default {
  name: 'MenuList',
}
</script>

<style lang="scss">
.MenuList {
  margin: 0;
  padding: .75rem 1rem;
  list-style-type: none;
}
</style>