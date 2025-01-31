<template lang="html">
  <div class="user-wrapper">
    <aside class="user-aside">
      <header class="user-header">
        <router-link class="user-header-title" to="/users/">
          <span>
            <i class="fas fa-chevron-left"></i>
          </span>
          Account Management
        </router-link>
        <div class="user-header-avatar" :class="data.avatar.url && data.avatar.url !== 'https://placehold.co/500x500/' ? 'uploaded' : ''">
          
          <img :src="data.avatar.url" alt="">
        </div>
        <label for="user-header-avatar" class="user-header-upload">
          <input type="file" hidden id="user-header-avatar" @input="getInputFile($event as any)">
          <span>Upload Photo</span>
        </label>
      </header>
    </aside>
    <div class="user-container">
      <section class="user-section">
        <h2 class="user-section-title">
          profile information
          <span class="user-section-save">Save</span>
        </h2>
        <div class="user-section-cards">
          <label class="user-section-card" for="user-username">
            <span>Username</span>
            <input type="text" id="user-username" placeholder="John Doe">
          </label>
          <label class="user-section-card" for="user-firstname">
            <span>First name</span>
            <input type="text" id="user-firstname" placeholder="John">
          </label>
          <label class="user-section-card" for="user-lastname">
            <span>Last name</span>
            <input type="text" id="user-lastname" placeholder="Doe">
          </label>
          <label class="user-section-card" for="user-email">
            <span>Email</span>
            <input type="email" id="user-email" placeholder="example@example.com">
          </label>
        </div>
      </section>
      <section class="user-section">
        <h2 class="user-section-title">contact information</h2>
        <div class="user-section-cards">
          <label class="user-section-card" for="user-contact-email">
            <span>Email</span>
            <input type="text" id="user-contact-email" placeholder="example@example.com">
          </label>
          <label class="user-section-card" for="user-telegram">
            <span>Telegram</span>
            <input type="text" id="user-telegram" placeholder="t.me/@username">
          </label>
          <label class="user-section-card" for="user-website">
            <span>Website</span>
            <input type="text" id="user-website" placeholder="example.com">
          </label>
          <label class="user-section-card" for="user-phonenumber">
            <span>Phone number</span>
            <input type="email" id="user-phonenumber" placeholder="example@example.com">
          </label>
        </div>
      </section>
      <section class="user-section">
        <label class="user-section-about-label" for="user-section-about">
          <h2 class="user-section-title">about the user</h2>
          <textarea name="user-section-about" id="user-section-about">Lorem ipsum dolor sit, amet consectetur adipisicing elit. Distinctio rerum ad mollitia doloremque magni, quos quae sint error molestias explicabo est id velit eum molestiae et, tempora dolorem tempore optio.
          </textarea>
        </label>
      </section>

    </div>
  </div>
</template>

<script lang="ts" setup>
import { useRoute } from 'vue-router';
import { ref } from 'vue'
const route = useRoute();
const id = route.params.id;

const data = ref({
  avatar: {
    url: "https://placehold.co/500x500/" as string,
    file: null as File | null
  }
})

const getInputFile = (event: any) => {
  const target = event.target;
  if (target.files && target.files[0] && data.value.avatar.url === 'https://placehold.co/500x500/') {
    const file = target.files[0];

    const reader = URL.createObjectURL(target.files[0]);
    data.value.avatar.url = reader;


    return false;
  }

  else alert("Please select one valid image or try again.")
}
</script>

<style scoped lang="scss">
.user {
  &-wrapper {
    display: flex;
    align-items: flex-start;

    @media(max-width: 575px) {
      flex-direction: column;
    }
  }

  &-header {
    display: flex;
    flex-direction: column;
    align-items: flex-start;
    justify-content: flex-start;
    max-width: 32rem;
    width: 100%;
    padding: 2rem;
    position: relative;

    @media(max-width: 575px) {
      max-width: 100%;
    }

    &-title {
      font-size: 1.6rem;
      font-weight: 400;
      line-height: 125%;
      display: flex;
      align-items: center;
      justify-content: flex-start;
      column-gap: 1rem;
      cursor: pointer;
      color: black;

      &:hover {
        & * {
          color: black;
        }
      }

      & span {
        & i {
          color: rgba(0, 0, 0, 0.2);
        }
      }
    }

    &-avatar {
      width: 25rem;
      height: 25rem;
      margin: 2rem 0 1.2rem;
      border-radius: .4rem;
      overflow: hidden;

      &.uploaded {
        background-color: black;
      }

      @media(max-width: 575px) {
        margin: 2rem auto;
        background: unset;
        border-radius: 50%;
      }

      @media(max-width: 400px) {
        width: 15rem;
        height: 15rem;
      }

      & img {
        width: 100%;
        height: 100%;
        object-fit: contain;
        border-radius: .4rem;

        @media(max-width: 575px) {
          border-radius: 50%;
        }
      }
    }

    &-upload {
      background: #eee;
      width: 100%;
      height: auto;
      padding: .8rem;
      border-radius: .6rem;
      display: flex;
      align-items: center;
      justify-content: center;

      & span {
        background: white;
        width: 100%;
        height: 100%;
        padding: 1.2rem;
        font-size: 1.2rem;
        line-height: 125%;
        text-align: center;
        font-weight: 500;
        color: rgba(0, 0, 0, 0.5);
        border-radius: inherit;
        transition: 300ms;

        &:hover {
          color: black;
        }
      }
    }
  }

  &-aside {
    width: 35rem;

    @media(max-width: 575px) {
      width: 100%;
    }
  }

  &-container {
    width: 100%;
    height: 100%;
    padding-top: 2rem;

    @media(max-width: 575px) {
      padding: 2rem;
    }
  }

  &-section {
    padding: 2rem;
    border: .1rem solid #eee;
    margin-bottom: 1.2rem;

    &-save {
      background: #2563eb;
      color: white;
      font-size: 1.4rem;
      font-weight: 400;
      line-height: 100%;
      color: white;
      width: 8rem;
      height: 3rem;
      border-radius: .4rem;
      display: flex;
      align-items: center;
      justify-content: center;
    }

    &-title {
      font-size: 1.6rem;
      font-weight: 500;
      text-transform: capitalize;
      color: rgba(0, 0, 0);
      width: 100%;
      display: flex;
      align-items: center;
      justify-content: space-between;
    }

    &-cards {
      margin-top: 2rem;
      display: flex;
      align-items: center;
      justify-content: flex-start;
      flex-wrap: wrap;
      gap: 1.2rem;

      &>label {
        max-width: calc(100% / 2 - .6rem);
        width: 100%;
        display: flex;
        flex-direction: column;
        align-items: flex-start;
        justify-content: flex-start;
        row-gap: .4rem;

        @media(max-width: 768px) {
          max-width: 100%;
        }

        &:hover {
          & * {
            color: black;
          }
        }

        & span,
        h1,
        h2,
        h3,
        h4,
        h5,
        h6 {
          font-size: 1.4rem;
          color: rgba(0, 0, 0, 0.5);
        }

        & input {
          width: 100%;
          height: 100%;
          padding: 1rem;
          outline: none;
          border: .1rem solid #eee;
          border-radius: .4rem;
        }
      }
    }

    &-about {
      &-label {
        width: 100%;
        height: 100%;
        display: flex;
        flex-direction: column;
        align-items: flex-start;
        justify-content: flex-start;

        & textarea {
          font-family: sans-serif;
          font-size: 1.6rem;
          margin-top: 1.2rem;

          &#user-section-about {
            resize: none;
            height: 10rem;
            width: 100%;
            padding: 1rem;
            outline: none;
            border: .1rem solid #eee;
            transition: 300ms;

            @media(max-width: 575px) {
              &:focus {
                height: 25rem;
              }
            }

            @media(max-width: 400px) {
              font-size: 1.4rem;

              &:focus {
                height: 20rem;
              }
            }
          }
        }
      }

    }
  }
}
</style>