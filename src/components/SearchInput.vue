<template>
  <div class="SearchInput">
    <img src="../assets/icons/search.svg">
    <input type="text" placeholder="Search">
  </div>
</template>

<script>
export default {
  name: 'SearchInput',
}
</script>

<style lang="scss">
.SearchInput {
  border: 1px solid white;
  display: flex;
  align-items: center;
  justify-content: flex-start;

  background: var(--white);
  border-radius: 4rem;
  padding: .25rem;

  width: 175px;

  img {
    margin-right: 0.5em;
  }

  input {
    background: transparent;
    outline: none;
    border: none;

    width: 100%;
    font-size: .8rem;
  }
}
</style>