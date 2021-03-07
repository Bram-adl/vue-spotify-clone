<template>
  <div class="MusicCard">
    <div class="MusicCard--Banner">
      <div class="MusicCard--Controllers">
        <svg width="12" height="11" viewBox="0 0 12 11" fill="none" xmlns="http://www.w3.org/2000/svg" class="heart">
          <path fill-rule="evenodd" clip-rule="evenodd" d="M7.45657 0.247537C7.85098 0.0841142 8.27372 0 8.70064 0C9.12757 0 9.55031 0.0841143 9.94472 0.247537C10.3391 0.410931 10.6973 0.650403 10.9991 0.952276C11.301 1.25405 11.5406 1.6125 11.704 2.00684C11.8674 2.40125 11.9516 2.82399 11.9516 3.25091C11.9516 3.67784 11.8674 4.10058 11.704 4.49499C11.5406 4.88936 11.3011 5.24767 10.9992 5.54947C10.9992 5.54949 10.9992 5.54944 10.9992 5.54947L6.5792 9.96947C6.38394 10.1647 6.06735 10.1647 5.87209 9.96947L1.45209 5.54947C0.842478 4.93985 0.5 4.11304 0.5 3.25091C0.5 2.38879 0.842478 1.56197 1.45209 0.952359C2.06171 0.342745 2.88852 0.000267386 3.75065 0.000267386C4.61277 0.000267386 5.43958 0.342745 6.0492 0.952359L6.22565 1.12881L6.40201 0.952442C6.40204 0.952415 6.40198 0.95247 6.40201 0.952442C6.7038 0.65053 7.0622 0.410946 7.45657 0.247537ZM8.70064 1C8.40508 1 8.11241 1.05823 7.83936 1.17137C7.56631 1.28451 7.31823 1.45034 7.10928 1.65938L6.5792 2.18947C6.38394 2.38473 6.06735 2.38473 5.87209 2.18947L5.34209 1.65947C4.92001 1.23739 4.34755 1.00027 3.75065 1.00027C3.15374 1.00027 2.58128 1.23739 2.1592 1.65947C1.73712 2.08154 1.5 2.654 1.5 3.25091C1.5 3.84782 1.73712 4.42028 2.1592 4.84236L6.22565 8.90881L10.2921 4.84236C10.5011 4.63341 10.667 4.38525 10.7802 4.11219C10.8933 3.83914 10.9516 3.54648 10.9516 3.25091C10.9516 2.95535 10.8933 2.66268 10.7802 2.38963C10.667 2.11658 10.5012 1.86849 10.2922 1.65955C10.0832 1.45051 9.83498 1.28451 9.56193 1.17137C9.28888 1.05823 8.99621 1 8.70064 1Z" fill="#FCFCFC"/>
        </svg>

        <svg width="21" height="20" viewBox="0 0 21 20" fill="none" xmlns="http://www.w3.org/2000/svg" class="play">
          <path d="M15.5 10.1962L6.5 15.3923L6.5 5L15.5 10.1962Z" fill="white"/>
        </svg>

        <svg width="16" height="16" viewBox="0 0 16 16" fill="none" xmlns="http://www.w3.org/2000/svg" class="dots">
          <path fill-rule="evenodd" clip-rule="evenodd" d="M6.66666 8.00002C6.66666 7.26364 7.26362 6.66669 8 6.66669C8.73638 6.66669 9.33333 7.26364 9.33333 8.00002C9.33333 8.7364 8.73638 9.33335 8 9.33335C7.26362 9.33335 6.66666 8.7364 6.66666 8.00002Z" fill="#FCFCFC"/>
          <path fill-rule="evenodd" clip-rule="evenodd" d="M11.3333 8.00002C11.3333 7.26364 11.9303 6.66669 12.6667 6.66669C13.403 6.66669 14 7.26364 14 8.00002C14 8.7364 13.403 9.33335 12.6667 9.33335C11.9303 9.33335 11.3333 8.7364 11.3333 8.00002Z" fill="#FCFCFC"/>
          <path fill-rule="evenodd" clip-rule="evenodd" d="M2 8.00002C2 7.26364 2.59695 6.66669 3.33333 6.66669C4.06971 6.66669 4.66667 7.26364 4.66667 8.00002C4.66667 8.7364 4.06971 9.33335 3.33333 9.33335C2.59695 9.33335 2 8.7364 2 8.00002Z" fill="#FCFCFC"/>
        </svg>
      </div>
    </div>

    <div class="MusicCard--Label">
      {{ label }}
    </div>

    <div class="MusicCard--Description">
      {{ desc }}
    </div>

    <div class="MusicCard--Detail">
      {{ detail }}
    </div>
  </div>
</template>

<script>
export default {
  name: 'MusicCard',

  props: {
    label: {
      type: String,
      required: true,
    },

    desc: {
      type: String,
      required: false,
    },

    detail: {
      type: String,
      required: false,
    },
  },
}
</script>

<style lang="scss">
.MusicCard {
  &:hover &--Controllers {
    display: flex;
  }
  
  &--Banner {
    position: relative;
    
    width: 100%;
    padding-top: 100%;
    height: auto;

    background: url('../assets/images/on_repeat.png') center center/cover;

    &:hover {
      background: 
        linear-gradient(rgba(0, 0, 0, 0.5), rgba(0, 0, 0, 0.25)), 
        url('../assets/images/on_repeat.png') center center/cover;
    }
  }

  &--Controllers {
    position: absolute;
    top: 50%;
    left: 50%;
    transform: translate(-50%, -50%);
    width: 100%;
    height: auto;

    display: flex;
    align-items: center;
    justify-content: center;

    display: none;

    svg {
      width: 1.25rem;
      height: 1.25rem;
      cursor: pointer;
    }

    .play {
      width: 3rem;
      height: 3rem;
      margin: 0 2rem;
      border: 2px solid white;
      border-radius: 50%;
      transition: .1s ease-out;

      &:hover {
        width: 3.25rem;
        height: 3.25rem;
      }
    }
  }

  &--Label {
    display: inline-block;
    color: var(--white);
    font-size: .9rem;
    margin: .75rem 0 .5rem;
    cursor: pointer;

    &:hover {
      text-decoration: underline;
    }
  }

  &--Description,
  &--Detail {
    font-size: .8rem;
    line-height: 1.5;
  }

  &--Detail {
    text-transform: uppercase;
  }
}
</style>