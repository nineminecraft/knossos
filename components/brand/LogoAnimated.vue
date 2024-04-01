<template>
  <div>
    <img style="height: 5rem" src="~/assets/best_thing.png">
  </div>
</template>

<style lang="scss" scoped>
div {
  display: flex;
  justify-content: center;
  align-items: center;
  height: 5rem;
  margin-top: 1rem;

  svg {
    width: 5rem;
    height: 5rem;
    position: absolute;

    @keyframes rotateAndBob {
      0% {
        transform: scale(1.0);
      }

      10% {
        transform: scale(1.2);
      }

      20% {
        transform: scale(1);
      }

      30% {
        transform: scale(1.2);
      }

      40% {
        transform: scale(1);
      }

      50% {
        transform: scale(1.2);
      }

      60% {
        transform: scale(1.0);
      }

      70% {
        transform: scale(1.2);
      }

      80% {
        transform: scale(1);
      }

      90% {
        transform: scale(1.2);
      }

      100% {
        transform: scale(1.0);
      }
    }

    &.rotate {
      //animation: rotate 1s infinite linear;
      animation: rotateAndBob 4s ease-in-out infinite;

      &.inner {
        animation: rotate 6s infinite linear reverse;
      }
    }

    @keyframes rotate {
      0% {
        transform: rotate(0);
      }

      100% {
        transform: rotate(360deg);
      }
    }
  }
}
</style>
