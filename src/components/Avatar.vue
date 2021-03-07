<template>
  <div class="Avatar">
		<img src="../assets/images/avatar.jpeg" class="Avatar-Image">
		<div class="Avatar-Name">
			Bram
		</div>
	</div>
</template>

<script>
export default {
	name: 'Avatar',
}
</script>

<style lang="scss">
.Avatar {
  display: flex;
  align-items: center;
  justify-content: center;

  &:hover .Avatar-Name {
    text-decoration: underline;
    color: var(--white);
  }

  &-Image {
    width: 2rem;
    height: 2rem;
    object-fit: cover;
    border-radius: 50%;
  }

  &-Name {
    margin-left: .5rem;
    font-size: .9rem;
    cursor: pointer;
  }
}
</style>