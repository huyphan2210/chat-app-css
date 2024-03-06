<script lang="ts">
export default {
  name: "chat-comment",
  props: {
    content: String,
    isRight: Boolean,
  },
};
</script>

<template>
  <p :class="isRight ? 'chat-right' : 'chat-left'">{{ content }}</p>
</template>

<style lang="scss" scoped>
p {
  margin-block: 0;
  padding: 1rem;
  font-size: 0.8rem;
  width: 60%;
  margin-bottom: 1rem;

  &.chat-left {
    color: var(--chat-left);
    background-color: var(--sub-heading);
    border-radius: 2rem 2rem 2rem 0;
  }

  &.chat-right {
    color: var(--chat-right);
    background-color: white;
    border-radius: 2rem 2rem 0 2rem;
    margin-left: calc(40% - 2rem);
  }
}
</style>
