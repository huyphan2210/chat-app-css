<script lang="ts">
export default {
  name: "special-shape",
};
</script>

<template>
  <div class="special-shape"></div>
</template>

<style lang="scss" scoped>
.special-shape {
  position: absolute;
  height: 60vh;
  width: 50vw;
  background-color: var(--background);
  border-radius: 100% 0 0 0;
  bottom: 0;
  left: 50%;
  z-index: -1;

  &.gradient {
    background: linear-gradient(
      225deg,
      var(--gradient-top),
      var(--gradient-bottom)
    );
    border-radius: 0 0 100% 0;
    top: 0;
    left: 0;
  }
}

@media screen and (min-width: 1440px) {
  .special-shape {
    width: 30vw;
    border-radius: 37.5vh 37.5vh 0 0;
    left: 75%;
    height: 75vh;

    &.gradient {
      border-radius: 0 0 37.5vh 37.5vh;
      left: -5%;
    }
  }
}
</style>
