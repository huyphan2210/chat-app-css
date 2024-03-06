<script lang="ts">
import avatar from "../../assets/images/avatar.jpg";
import Comment from "./Comment/Comment.vue";

export default {
  name: "phone-illustration",
  data() {
    return {
      avatar,
    };
  },
  components: {
    Comment,
  },
};
</script>

<template>
  <section class="phone">
    <article class="phone__chat-app">
      <header class="phone__chat-app__header">
        <div class="phone__chat-app__header__left">
          <button type="button" title="Back button">
            <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 320 512">
              <path
                fill="white"
                d="M9.4 233.4c-12.5 12.5-12.5 32.8 0 45.3l192 192c12.5 12.5 32.8 12.5 45.3 0s12.5-32.8 0-45.3L77.3 256 246.6 86.6c12.5-12.5 12.5-32.8 0-45.3s-32.8-12.5-45.3 0l-192 192z"
              />
            </svg>
          </button>
          <figure>
            <img :src="avatar" loading="lazy" alt="Avatar" />
            <figcaption>
              <h3>Samuel Green</h3>
              <span>Available to Walk</span>
            </figcaption>
          </figure>
        </div>
        <button type="button" title="More button">
          <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 128 512">
            <path
              fill="white"
              d="M64 360a56 56 0 1 0 0 112 56 56 0 1 0 0-112zm0-160a56 56 0 1 0 0 112 56 56 0 1 0 0-112zM120 96A56 56 0 1 0 8 96a56 56 0 1 0 112 0z"
            />
          </svg>
        </button>
      </header>
      <main class="phone__chat-app__body">
        <div class="phone__chat-app__body__content">
          <Comment content="That sounds great. I’d be happy with that." />
          <Comment content="Could you send over some pictures of your dog, please?" />
          <Comment content="Here are a few pictures. She’s a happy girl!" isRight />
          <Comment content="Can you make it?" isRight />
          <Comment content="She looks so happy! The time we discussed works. How long shall I take her out for?" />
        </div>
        <form submit class="phone__chat-app__body__input">
          <input disabled placeholder="Type your message..." />
          <button type="submit" title="Submit button">
            <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 320 512">
              <path
                fill="white"
                d="M9.4 233.4c-12.5 12.5-12.5 32.8 0 45.3l192 192c12.5 12.5 32.8 12.5 45.3 0s12.5-32.8 0-45.3L77.3 256 246.6 86.6c12.5-12.5 12.5-32.8 0-45.3s-32.8-12.5-45.3 0l-192 192z"
              />
            </svg>
          </button>
        </form>
      </main>
    </article>
  </section>
</template>

<style lang="scss" scoped>
.phone {
  background-color: white;
  border-radius: 2rem;
  box-shadow: 0 0 1rem -10px rgba(0, 0, 0, 0.85);
  padding: 1rem;
  min-height: 60vh;
  max-width: 20rem;
  display: flex;
  flex-direction: column;

  &__chat-app {
    background-color: var(--background);
    flex-grow: 1;
    height: 100%;
    border-radius: 1rem;
    position: relative;
    display: flex;
    flex-direction: column;

    &__header {
      padding: 3rem 1rem 1rem;
      background: linear-gradient(
        to right,
        var(--gradient-bottom),
        var(--gradient-top)
      );
      border-radius: 1rem;
      display: flex;
      justify-content: space-between;
      align-items: center;

      &__left {
        display: flex;
        gap: 0.5rem;
        align-items: center;

        img {
          width: 2rem;
          aspect-ratio: 1;
          border-radius: 50%;
          outline: 1px solid white;
        }

        figure {
          margin: 0;
          display: flex;
          align-items: center;
          gap: 0.5rem;
          figcaption {
            h3 {
              margin-block: 0;
              font-size: 1rem;
              color: white;
            }

            span {
              font-size: 0.7rem;
              color: var(--placeholder);
            }
          }
        }
      }

      button {
        width: 0.8rem;
        background: transparent;
        border: none;
        padding: 0;
        display: flex;
        transition: 0.3s;

        svg {
          width: 100%;
          aspect-ratio: 0.5;
        }

        &:hover {
          cursor: pointer;
          opacity: 0.7;
        }
      }
    }

    &__body {
      padding: 1rem;
      flex-grow: 1;
      position: relative;
      display: flex;
      flex-direction: column;

      &__content {
        flex-grow: 1;
      }

      &__input {
        position: relative;
        input {
          width: calc(100% - 5rem);
          border: none;
          border-radius: 2rem;
          padding: 1rem 4rem 1rem 1rem;
          font-family: Rubik, sans-serif;

          &:disabled {
            background-color: white;
          }

          &::placeholder {
            color: var(--placeholder);
          }
        }
        button {
          position: absolute;
          right: 1rem;
          top: 50%;
          border: none;
          border-radius: 50%;
          background-color: var(--button-bg);
          transform: translate(0, -50%);
          width: 2rem;
          height: 2rem;
          padding: 0.5rem;
          svg {
            height: 100%;
            rotate: 180deg;
          }
        }
      }
    }

    &::before {
      content: "";
      position: absolute;
      left: 50%;
      top: 0;
      transform: translate(-50%);
      background-color: white;
      width: 50%;
      height: 1.5rem;
      border-radius: 0 0 1rem 1rem;
    }
  }
}
</style>
