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
      <hgroup>
        <h1>Simple Booking</h1>
        <p>
          Stay in touch with our dog walkers through the chat interface. This
          makes it easy to discuss arrangements and make bookings. Once the walk
          has been completed you can rate your walker and book again all through
          the chat.
        </p>
      </hgroup>
    </div>
  </main>
</template>

<style lang="scss" scoped>
main {
  position: relative;
  flex-grow: 1;
  padding: 10vh clamp(10vw, 2rem, 15vw);

  .content {
    width: 100%;
    display: flex;
    justify-content: center;
    align-items: center;
    flex-direction: column;

    hgroup {
      margin-top: 4rem;
      text-align: center;

      h1 {
        color: var(--main-heading);
        margin-top: 0;
        font-size: clamp(2rem, 10vw, 3rem);
      }

      p {
        line-height: clamp(1.5rem,8vw, 3rem);
        color: var(--paragraph);
        font-size: clamp(1rem, 5vw, 1.2rem);
      }
    }
  }
}

@media screen and (min-width: 1440px) {
  main {
    padding-inline: clamp(15vw, 15rem, 20vw);
    .content {
      flex-direction: row;
      gap: clamp(8vw, 10rem, 10vw);
      transform: scale(0.9);

      hgroup {
        text-align: start;
      }
    }
  }
}
</style>
