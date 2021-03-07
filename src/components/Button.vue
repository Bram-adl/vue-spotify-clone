<template>
  <div class="Button">
    {{ text }}
  </div>
</template>

<script>
export default {
  name: 'Button',

  props: {
    text: {
      type: String,
      required: true,
    },
  },
}
</script>

<style lang="scss">
.Button {
  display: inline-block;
  
  border: 1px solid var(--white);
  border-radius: 100px;
  
  margin: 2rem auto 0;
  padding: .5rem 2rem;

  color: var(--white);
  font-size: .6rem;
  text-align: center;
  text-transform: uppercase;
  letter-spacing: 2px;

  cursor: pointer;
  transition: .1s ease-out;

  &:hover {
    transform: scale(1.1);
  }
}
</style>