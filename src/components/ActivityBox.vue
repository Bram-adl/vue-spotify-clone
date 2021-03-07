<template>
  <div class="ActivityBox">
    <div class="Activity-Avatar">
      <img src="../assets/images/avatar.jpeg" width="50" height="50">
    </div>

    <div class="Activity-Profile">
      <div class="Profile-Name">
        <div class="Name">
          {{ name }}
        </div>
        <div class="PlayStatus">
          <img src="../assets/icons/playing.svg" alt="playing" v-if="isPlaying">
          <span v-else>
            {{ lastPlaying }}
          </span>
        </div>
      </div>

      <div class="Profile-Song">
        <div class="Song-Title">
          {{ songTitle }}
        </div>
        <div class="Song-Artist">
          {{ songArtist }}
        </div>
        <div class="Song-Resource">
          <img src="../assets/icons/music.svg" alt="music">
          <span>
            {{ songResource }}
          </span>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'ActivityBox',

  props: {
    name: {
      type: String,
      required: true,
    },

    isPlaying: {
      type: Boolean,
      required: true,
    },

    lastPlaying: {
      type: String,
      required: false,
    },

    songTitle: {
      type: String,
      required: true,
    },

    songArtist: {
      type: String,
      required: true,
    },

    songResource: {
      type: String,
      required: true,
    },
  },
}
</script>

<style lang="scss">
.ActivityBox {
  display: flex;
  align-items: center;
  justify-content: space-between;
  margin: 1rem 0;
  text-align: left;
}

.Activity-Avatar {
  margin-right: 1rem;
  line-height: 0;

  img {
    width: 2.5rem;
    height: 2.5rem;
    border-radius: 50%;
    object-fit: cover;
  }
}

.Activity-Profile {
  // border: 1px solid white;
  font-size: 0.8rem;
  line-height: 1.5;
  flex: 1;
  overflow: hidden;

  .Profile-Name {
    display: flex;
    align-items: center;
    justify-content: space-between;
    margin-bottom: 0.25rem;

    .Name {
      color: var(--white);
      cursor: pointer;

      &:hover {
        text-decoration: underline;
      }
    }
  }

  .Profile-Song {
    font-size: 0.7rem;

    .Song-Title,
    .Song-Artist,
    .Song-Resource {
      width: 100%;
      overflow: hidden;
      text-overflow: ellipsis;
      white-space: nowrap;
    }

    .Song-Resource {
      margin-top: 0.5rem;
      display: flex;
      align-items: center;

      img {
        margin-right: 0.5em;
      }

      span {
        text-overflow: ellipsis;
        overflow: hidden;
        white-space: nowrap;
      }
    }
  }
}
</style>