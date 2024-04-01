<template>
  <div style="display: flex; flex-direction: row; gap: 1rem; align-items: center">
    <img style="height: 2rem" src="~/assets/best_thing.png"> <span style="font-family: cursive"> nineMinecraft </span>
  </div>
</template>

<script setup>
const loading = useLoading()
</script>

<style lang="scss" scoped>
.animate {
  .ring {
    transform-origin: center;
    transform-box: fill-box;
    animation-fill-mode: forwards;
    transition: transform 2s ease-in-out;

    &--large {
      animation: spin 1s ease-in-out infinite forwards;
    }

    &--small {
      animation: spin 2s ease-in-out infinite reverse;
    }
  }

  @keyframes spin {
    from {
      transform: rotate(0deg);
    }

    to {
      transform: rotate(360deg);
    }
  }
}
</style>
