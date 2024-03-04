<script lang="ts">
export default {
  name: "phone-illustration",
};
</script>

<template>
  <div class="phone">
    <div class="phone__chat-app"></div>
  </div>
</template>

<style lang="scss" scoped>
.phone {
  background-color: white;
  border-radius: 2rem;
  box-shadow: 0 0 1rem -10px rgba(0, 0, 0, 0.85);
  padding: 1rem;
  height: 60vh;

  &__chat-app {
    background-color: var(--background);
    height: 100%;
    border-radius: 1rem;
  }
}
</style>
