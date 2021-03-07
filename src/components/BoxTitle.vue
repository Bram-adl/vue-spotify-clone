<template>
  <div class="BoxTitle">{{ title }}</div>
</template>

<script>
export default {
  name: 'BoxTitle',
  
  props: {
    title: {
      type: String,
      required: true,
    },
  },
}
</script>

<style lang="scss">
.Title {
  color: var(--white);
}
</style>