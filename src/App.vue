<script setup lang="ts">
import SpecialShape from "./components/SpecialShape.vue";
import Phone from "./components/Phone/Phone.vue";
</script>

<template>
  <main>
    <special-shape class="gradient" />
    <special-shape />
    <div class="content">
      <phone />
    </div>
  </main>
</template>

<style lang="scss" scoped>
main {
  position: relative;
  flex-grow: 1;
  padding: 10vh 15vw;

  .content {
    width: 70vw;
  }
}
</style>
