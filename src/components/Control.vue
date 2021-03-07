<template>
  <div class="Control">
    <svg class="Control--Item Control--Prev"  width="9" height="16" viewBox="0 0 9 16" fill="none" xmlns="http://www.w3.org/2000/svg">
      <path fill-rule="evenodd" clip-rule="evenodd" d="M0.530797 6.87108L7.67071 0.623657L8.32922 1.37623L1.1893 7.62366C0.961639 7.82286 0.961639 8.17703 1.1893 8.37623L8.32922 14.6237L7.67071 15.3762L0.530798 9.12881C-0.152192 8.53119 -0.152194 7.4687 0.530797 6.87108Z" fill="#8B8B8B"/>
    </svg>
    <svg class="Control--Item Control--Next" width="9" height="16" viewBox="0 0 9 16" fill="none" xmlns="http://www.w3.org/2000/svg">
      <path fill-rule="evenodd" clip-rule="evenodd" d="M8.4692 6.87108L1.32929 0.623657L0.670785 1.37623L7.8107 7.62366C8.03836 7.82286 8.03836 8.17703 7.8107 8.37623L0.670785 14.6237L1.32929 15.3762L8.4692 9.12881C9.15219 8.53119 9.15219 7.4687 8.4692 6.87108Z" fill="#F3F3F3"/>
    </svg>
  </div>
</template>

<script>
export default {

}
</script>

<style lang="scss">
.Control {
  display: flex;
  align-items: center;
  justify-content: center;

  &--Item {
    margin-right: 1rem;
    cursor: pointer;
  }
}
</style>