<template>
  <div class="CreateNewPlaylist">
    <svg width="23" height="23" viewBox="0 0 23 23" fill="none" xmlns="http://www.w3.org/2000/svg">
      <rect x="11" y="5" width="1" height="13" fill="#B3B3B3"/>
      <rect x="18" y="11" width="1" height="13" transform="rotate(90 18 11)" fill="#B3B3B3"/>
      <circle cx="11.5" cy="11.5" r="11" stroke="#B3B3B3"/>
    </svg>

    <span>New Playlist</span>
  </div>
</template>

<script>
export default {
  name: 'CreateNewPlaylist',
}
</script>

<style lang="scss">
.CreateNewPlaylist {
  width: 100%;
  height: auto;
  margin: 0;
  padding: 1rem 1.25rem;

  display: flex;
  align-items: center;
  justify-content: flex-start;
  
  border-top: 1px solid var(--white-shade);
  cursor: pointer;

  &:hover {
    svg rect {
      fill: #FFFFFF;
    }

    svg circle {
      stroke: #FFFFFF;
    }

    span {
      color: #FFFFFF;
    }
  }

  span {
    margin-left: 1rem;
    font-size: 0.8rem;
  }
}
</style>