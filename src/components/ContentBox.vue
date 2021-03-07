<template>
  <div class="ContentBox">
    <div class="ContentBox--Header">
      <BoxTitle :title="title" />
      <Control />
    </div>

    <div class="ContentBox--Body">
      <slot></slot>
    </div>
  </div>
</template>

<script>
import BoxTitle from '@/components/BoxTitle';
import Control from '@/components/Control';

export default {
  name: 'ContentBox',

  components: {
    BoxTitle,
    Control,
  },

  props: {
    title: {
      type: String,
      required: true,
    },
  },
}
</script>

<style lang="scss">
.ContentBox {
  margin: 2rem 0;
  padding: 0 1rem;

  &--Header {
    display: flex;
    align-items: center;
    justify-content: space-between;
    padding-bottom: 0.5rem;
    margin-bottom: 1rem;
    border-bottom: 1px solid var(--white-shade);
  }

  &--Body {
    width: 100%;
    overflow-x: auto;
    
    display: grid;
    grid-template-columns: repeat(4, 1fr);
    grid-gap: 1rem;
  }
}
</style>