<script lang="ts">
export default {
  name: "chat-comment",
  props: {
    content: String,
    isRight: Boolean,
    imgs: Array<string>,
    isRadio: Boolean,
    radioContent: String,
    radioPrice: Number,
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
  <div v-if="isRadio" class="chat-radio">
    <div class="chat-radio__left">
      <div class="chat-radio__left__button"></div>
      <span>{{ radioContent }}</span>
    </div>
    <span class="chat-radio__right"> ${{ radioPrice }} </span>
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
    background-color: var(--chat-left-bg);
    border-radius: 2rem 2rem 2rem 0;
    animation: slideInFromLeft 2s;
  }

  &.chat-right {
    color: var(--chat-right);
    background-color: white;
    border-radius: 2rem 2rem 0 2rem;
    margin-left: calc(40% - 2rem);
    animation: slideInFromRight 2s;
  }
}

.chat-images {
  display: flex;
  gap: 1rem;
  width: 70%;
  margin-bottom: 1rem;
  animation: slideInFromRight 2s;

  &.right {
    margin-left: 30%;
  }

  img {
    width: calc((100% - 2rem) / 3);
    border-radius: 1rem;
  }
}

.chat-radio {
  padding: 1rem;
  background: linear-gradient(
    to right,
    var(--gradient-top),
    var(--gradient-bottom)
  );
  border-radius: 2rem 2rem 2rem 0;
  width: 70%;
  margin-bottom: 1rem;
  color: white;
  display: flex;
  align-items: center;
  justify-content: space-between;
  gap: 1rem;
  animation: slideInFromLeft 2s;

  &__left {
    display: flex;
    align-items: center;
    gap: 0.5rem;

    &__button {
      aspect-ratio: 1;
      border-radius: 50%;
      border-color: white;
      border-style: solid;
      border-width: 0.1rem;
      background-color: transparent;
      width: 1.5rem;
    }

    span {
      font-size: 0.8rem;
    }
  }
}

@keyframes slideInFromLeft {
  0% {
    opacity: 0;
    transform: translate(-100%);
  }
  100% {
    opacity: 1;
  }
}

@keyframes slideInFromRight {
  0% {
    opacity: 0;
    transform: translate(100%);
  }
  100% {
    opacity: 1;
  }
}
</style>
