<script lang="ts">
export default {
  name: "chat-comment",
  props: {
    content: String,
    isRight: Boolean,
    imgs: Array<string>,
  },
};
</script>

<template>
  <p v-if="!!content" :class="isRight ? 'chat-right' : 'chat-left'">
    {{ content }}
  </p>
  <div v-if="!!imgs" class="chat-images" :class="isRight ? 'right' : 'left'">
    <img
      v-for="(img, i) in imgs"
      :key="i"
      :src="img"
      loading="lazy"
      :alt="'Dog' + i"
    />
  </div>
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

.chat-images {
  display: flex;
  gap: 1rem;
  width: 70%;
  margin-bottom: 1rem;

  &.right {
    margin-left: 30%;
  }

  img {
    width: calc((100% - 2rem) / 3);
    border-radius: 1rem;
  }
}
</style>
